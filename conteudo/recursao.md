# Recursão

[Allen Downey](https://books.trinket.io/thinkjava2/chapter8.html) define *recursividade* como o processo de chamar uma função que está sendo atualmente executada.

A ideia central é de que uma função pode chamar outras funções, e no caso de uma função recursiva, uma função pode também chamar ela mesma!

Para que isso funcione (e não caia em uma cilada conhecida como "recursão infinita") é preciso que a função em certas condições chegue em uma opção de execução que não requer chamar ela mesma, é o chamado "caso base".

### Exemplo 01

![imagem1](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/recursao/01recursao.jpg?raw=true)

```pde
void setup() {
  size(500, 500);
  noStroke();
  noLoop();
}

void draw() {
  desenharRetangulo(0, 0, 500, 10);
}

void desenharRetangulo(int x, int y, int tam, int level) {                    
  stroke(0);
  rect(x, y, tam, tam);      
  if (level > 1) {
    level = level - 1;
    desenharRetangulo(x, y, tam/2, level);
    desenharRetangulo(x + tam, y, tam/2, level);
  }
}
```

### Exemplo 02

![2](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/recursao/recursao2003.jpg?raw=true)

![3](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/recursao/recursao2005.jpg?raw=true)

Comente a linha:

//desenhaCirculo(x, y - d/2, d/2);

![4](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/recursao/recursao2038.jpg?raw=true)

Comente as linhas:

//desenhaCirculo(x, y + d/2, d/2);

//desenhaCirculo(x, y - d/2, d/2);

![5](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/recursao/recursao2049.jpg?raw=true)

Comente as linhas:

//desenhaCirculo(x + d/2, y, d/2);

//desenhaCirculo(x, y + d/2, d/2);

//desenhaCirculo(x, y - d/2, d/2);

```pde
void setup() {
  size (701, 701);
}

void draw() {
  desenhaCirculo(width/2, height/2, 300);
}

void desenhaCirculo(float x, float y, float d) {
  ellipse(x, y, d, d);
  if (d > 2) {
    desenhaCirculo(x - d/2, y, d/2);
    desenhaCirculo(x + d/2, y, d/2);
    desenhaCirculo(x, y + d/2, d/2);
    desenhaCirculo(x, y - d/2, d/2);
  }
}
```

