#  Orientação a objetos com caminhantes aleatórios

Inspirado na introdução à simulações físicas apresentada por Daniel Shiffman em *Nature of Code*, 
este tutorial que se desenvolve  em etapas  serão introduz alguns conceitos de orientação a objetos: Classe, atributos de dados e métodos, instâncias e encapsulamento.

Não são abordadas as questões de herança e composição. Para poder aproveitar o exemplo sugerimos que você revise antes o seguinte vocabulário e algumas ideias de programação:

* Métodos de desenho `rect`, `line`, `ellipse`, `beginShape`, `vertex` e `endShape`;
* Controle de atributos gráficos `fill`, `stroke`, `noStroke`, `noFill`, `background`;
* Controle de fluxo de execução e laços `if`, `else`, `for`;
* Declaração de funções com e sem parâmetros;
<!-- * Controle do sistema de coordenadas `pushMatrix`, `translate`, `rotate`, `scale`, `popMatrix`. -->

## 1. Redesenhando formas e atualizando variáveis no laço principal

<img src="../assets/imagens/passo1.png" align="left" alt="output passo 1">

Para se obter o efeito de movimento (animação da particula) criamos um par de variáveis globais x e y, inicializadas no setup() com as coordenadas do meio da àrea de desenho. Note que o escopo global dessas variáveis precisa ser indicado com a palavra chave global quando pretendemos alterá-las.

O novo draw() cujo nome faz parte da infraestrutura do Processing para permitir animações, terá automaticamente a execução repetida continuamente, é o "laço principal" do sketch. Neste bloco vamos inicialmente limpar a tela com background() invocar a função de desenho particula() na posição indicada pelas variáveis x e y, incrementar as variáveis de posição e por fim checar se estas estão além de um certo limite e precisam ser alteradas (redefinindo a posição para um novo ciclo de incrementos).

```pde
float x, y;

void setup() {
  /* Código de configuração, executado no início pelo Processing */
  size(100, 100);  // área de desenho
  x = width / 2;
  y = height / 2;   // coordenadas do meio da área de desenho
}
void draw() {
  /* Laço principal de repetição do Processing */
  // background(0); // limpa o fundo
  circle(x, y, 50);  // desenha um círculo
  x = x + random(-5, 5);  // modifica o x
  y = y + random(-5, 5);  // modifica o y
  if (x > width + 25) x = -25;
  if (y > height + 25) y = -25;
  if (x < -25) x = width + 25;
  if (y < -25) y = height + 25;
  
}
```

## 2. Primeira aproximação da classe Particula

Vamos agora obter o mesmo comportamento usando um objeto da classe particula. A classe é definida pelo bloco class Particula{} que começa com o método Particula(), construtor de um novo objeto da classe e que inicializa os atributos de dados (campos) de posição e tamanho. O método desenha() é praticamente a função que escrevemos no passo inicial, não requer mais os parâmetros de posição e tamanho, uma vez que usa os atributos de posição e tamanho do próprio objeto (instância) quando executado. O método anda() contém o código anteriormente usado para atualizar a posição nas variáveis globais, agora atualiza os atributos de dados (campos ou variáveis de instância) de posição do objeto. No bloco setup() criamos uma instância de particula no meio da área de desenho com a linha Particula = new Particula(width / 2, height / 2, 50) e o bloco draw() vai repetidamente limpar a tela e chamar os métodos de desenho e atualização, Particula.desenha() e Particula.anda() respectivamente.

```pde
particula Particula; // variável global para uma particula

void setup() {
  /* define área de desenho e popula lista de particulas */
  size(100, 100);  // área de desenho
  float meia_largura = width / 2;
  float meia_altura = height / 2;
  Particula = new Particula(meia_largura, meia_altura, 50);
}

void draw() {
  /* Limpa a tela, desenha e atualiza particulas */
  background(0);  // atualização do desenho, fundo preto
  Particula.desenha();
  Particula.anda();
}

class particula {
  /* Classe particula */
  float x, y, tamanho;
  particula(float px, float py, float ptamanho) {
    x = px;
    y = py;
    tamanho = ptamanho;
  }

  void desenha() {
    circle(x, y, tamanho);  // desenha um círculo
  }

  void anda() {
    /* atualiza a posição do objeto e devolve do lado oposto se sair */
    x = x + random(-5, 5);  // modifica o x
    y = y + random(-5, 5);  // modifica o y
    if (x > width + 25) x = -25;
    if (y > height + 25) y = -25;
    if (x < -25) x = width + 25;
   if (y < -25) y = height + 25;
  }
}
```

## 3. Instanciando mais alguns objetos

A vantagem da estruturação e encapsulamento de termos um objeto Particula criado por uma classe particula pode começar a ser visto quando instanciamos mais de uma particula.

```pde
Particula particula_0, particula_1, particula_2; // lista de objetos

void setup() {
  /* define área de desenho e popula lista de particulas */
  size(100, 100);  // área de desenho
  float meia_largura = width / 2;
  float meia_altura = height / 2;
  particula_0 = new Particula(meia_largura, meia_altura, 50);
  particula_1 = new Particula(80, 10, 30);
  particula_2 = new Particula(10, 40, 20);
}

void draw() {
  /* Limpa a tela, desenha e atualiza particulas */
  background(0);  // atualização do desenho, fundo preto
  particula_0.desenha();
  particula_0.anda();
  particula_1.desenha();
  particula_1.anda();
  particula_2.desenha();
  particula_2.anda();
}
```

## 4. Ampliando a classe, mudando o comportamento e adicionando outras propriedades.

O passo seguinte é dado ampliando o código da classe particula.

No método construtor Particula():
1. Sorteio do tamanho, caso nenhum tenha sido passado 0 na expressão construtora;
2. Sorteio da velocidade, decomposta nos componentes horizontal vx e vertical vy;
3. Sorteio da cor, ligeiramente translúcida.

No método desenha():
2. Aplicação da cor de preenchimento com fill(cor).

No método anda():
1. Atualização da posição pela soma dos componentes de velocidade na posição;
2. Tratamento da saída do objeto da àrea de desenho por qualquer dos lados.

```pde
class Particula {
  /* Classe particula, cor sorteada, tamanho sorteado */
  float x, y, vx, vy, tamanho;
  color cor;
  Particula(float px, float py, float ptamanho) {
    x = px;
    y = py;
    if (ptamanho != 0) {
    tamanho = ptamanho;
    } else {
    tamanho = random(50, 200);
    }
    vx = random(-1, 1);
    vy = random(-1, 1);
    cor  = color(random(255), // R
                random(255), // G
                random(255), // B
                200);  // alpha
  }

  void desenha() {
    // se o mouse estiver longe, normal, senão, branca
    if (dist(mouseX, mouseY, x, y) > metade) {
      fill(cor);
    } else {
      fill(255, 100);

  void anda() {
    /* atualiza a posição do objeto e devolve do lado oposto se sair */

  }
}
```

## 5. Uma lista de objetos

Uma estrutura de dados, no caso uma lista do tipo ArrayList, pode de maneira muito simples conter referências para um grande número de objetos.
Aqui chegamos rapidamente a um comportamento visualmente interessante instanciando 50 particulas no setup() e em seguida no draw() iteramos por estas particulas com um tipo de laço conhecido como "for each" com a estrutura for (Tipo objeto : lista_de_objetos){ }. 

```pde
ArrayList<particula> particulas; // lista de objetos

void setup() {
  /* define área de desenho e popula lista de particulas */
  size(400, 400);  // área de desenho
  float meia_largura = width / 2;
  float meia_altura = height / 2;
  particulas = new ArrayList<particula>();
  for (int i=0; i <50; i++) {
    particulas.add(new Particula(meia_largura, meia_altura, 0));
  }
}

void draw() {
  /* Limpa a tela, desenha e atualiza particulas */
  background(0);  // atualização do desenho, fundo preto
  for (Particula p : particulas) {
    p.desenha();
    p.anda();
  }
}
```

## 6. Acrescentando e removendo objetos; Mudança da cor com o mouse próximo.

Como extra, acrescentamos exemplo dos métodos append() e remove() do ArrayList, chamados nos eventos de clique do mouse ou acionamento da barra de espaço no teclado, acrescentando ou removendo objetos respectivamente. O método de desenha() da particula agora sofre a influência da distância do mouse.


```pde
void mousePressed() {
  /* Acrescenta pequena particula branca */
  particula nova_particula = new Particula(mouseX, mouseY, 25);
  nova_particula.cor = color(255);  // forçando que seja branca!
  particulas.add(nova_particula);
}

void keyPressed() {  
  /* tecla 'espaço' remove a última particula da lista */
  int num_particulas =  particulas.size();
  if (key == ' ' && num_particulas > 1) {
     particulas.remove(num_particulas - 1);
  }
}

class Particula {
  /* Classe particula, cor sorteada, tamanho sorteado caso tamanho = 0 */
  float x, y, vx, vy, tamanho;
  color cor;
  Particula(float px, float py, float ptamanho) {
    x = px;
    y = py;
    if (ptamanho != 0) {
      tamanho = ptamanho;
    } else {
      tamanho = random(50, 200);
    }
    vx = random(-1, 1);
    vy = random(-1, 1);
    cor = color(random(255), // R
      random(255), // G
      random(255), // B
      200);  // alpha
  }

  void desenha() {
    /* Desenha polígono em torno das coordenadas do objeto */
    float metade = tamanho / 2;
    pushMatrix();   // preseservando o sistema de coordenadas anterior
    translate(x, y);  // translada o sistema de coordenadas
    noStroke() ; // sem contorno
    // se o mouse estiver longe, normal, senão, branca
    if (dist(mouseX, mouseY, x, y) > metade) {
      fill(cor);
    } else {
      fill(255, 100);
    }
    circle(x, y, tamanho);
  }
  void anda() {
    /* atualiza a posição do objeto e devolve do lado oposto se sair */
    x += vx;
    y += vy;
    float metade = tamanho / 2;
    if (x > width + metade) x = -metade;
    if (y > height + metade) y = -metade;
    if (x < -metade) x = width + metade;
    if (y < -metade) y = height + metade;
  }
}
```

### Referências:

VILLARES, Alexandre. B. A.; MOREIRA, Daniel. de C.; GOMES, Monica Rizzolli. [**Ensino de programação em um contexto de exploração gráfica com Processing modo Python.**](https://villares.github.io/mestrado/VILLARES_MOREIRA_GOMES_GRAPHICA_2017) GRAPHICA 2017: XII International Conference on Graphics Engineering for Arts and Design. 2017.

[Objects tutorial](https://processing.org/tutorials/objects/) by Daniel Shiffman @ Processing.org

