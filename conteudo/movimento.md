# Movimento

## A estrutura setup() e draw()

Para produzir movimento nos valemos de uma ideia presente em todo tipo de animação, a ideia dos *quadros* (*frames*) que são as imagens mostradas em uma rápida sucessão. No Processing a geração dessas imagens acontece dentro de uma função que devemos definir chamada `draw()`. Tudo que é desenhado dentro de `draw()` é na verdade redesenhado cerca de 60 vezes por segundo (o chamado *frame rate*). Para se obter o efeito de uma animação de elementos se deslocando na tela devemos "limpar" o quadro no começo de cada `draw()` frequentemente com a instrução `background()`. Se desenharmos sem essa "limpeza" da tela os elementos "acumulam" ou "deixam um rastro".

Antes do *laço principal de repetição*, que é como costumamos descrever a execução do `draw()`, é executada uma função de preparo ou configuração chamada `setup()` que também precisamos definir. Essas duas funções juntas são a forma mais comum de se estruturar um *sketch* (um programa em Processing).

Resumindo: Dentro do `setup()` vai tudo aquilo que precisamos fazer apenas uma vez e no começo, como, por exemplo, definir a àrea de desenho com `size()`. Já no `draw()` vão principalmente as instruções de desenho propriamente dito, em geral precedidas por uma limpeza da tela ou fundo, e são acionados os cálculos de atualização dos elementos da animação.

## Bounce

```pde
int raio = 50; // tamanho do raio da ellipse
float pX, pY; // posição inicial X e Y;   

float vX = random(-4, 4);  // Velocidade X inicial
float vY = random(-4, 4);  // Velocidade Y inicial

void setup() {
  size(640, 360);
  noStroke();
  frameRate(30);
  // ellipseMode(RADIUS) também usa os dois primeiros parâmetros da elipse () 
  // como o ponto central da forma, mas usa o terceiro e quarto parâmetros para
  // especificar a metade da largura e altura das formas.
  ellipseMode(RADIUS);
  // Definir posições iniciais
  pX = width/2;
  pY = height/2;
}

void draw() {
  background(255);

  // Atualizar a posição da ellipse
  pX = pX + vX ;
  pY = pY + vY ;

  // Testar se a ellipse está fora da tela
  // Se estiver, inverter a velocidade multiplicando por -1.
  if (pX > width-raio || pX < raio) {
    vX = -vX;
  }
  if (pY > height-raio || pY < raio) {
    vY = -vY;
  }

  // Desenhar a ellipse
  fill(0); // preenchimento preto
  noStroke(); // sem contorno
  ellipse(pX, pY, raio, raio);
}
```

![](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/bounce.gif?raw=true)

