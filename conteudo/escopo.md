# Escopo: variáveis locais e globais

## Variáveis locais e parâmetros nas definições de funções

Antes de usar uma variável no Processing é preciso que ela seja declarada, por exemplo `int i;`, `float angulo;` ou `color minhaCor;`, no mesmo momento podemos já atribuir um valor, isto é, apontar o nome da variável para um valor, como em `int i = 0;`, `color vermelho = color(255, 0, 0);` ou ainda `float redutor = 0.05;`

Quando a declaração de uma variável acontece dentro da definição de uma função (como `setup()`, por exemplo), dizemos que tem *escopo local* e somente o código dentro da função reconhece aquele nome e enxerga as atribuições dos valores realizadas neste escopo. Também os parâmetros ou argumentos na definição de um função com parâmetros pertencem ao escopo local da função.

### exemplo de uma variável local

```pde
void olho(float x, float y, float tamanho) {
  float metade = tamanho/2;    //metade é uma varivel local
  noStroke();
  fill(255);
  ellipse(x, y, tamanho, metade);
  fill(0);
  ellipse(x, y, metade-2, metade-2);
}
```

## Variáveis globais

Traducionalmente declaradas no início do *sketch*, e fora de qualquer função (incluindo `setup()` e `draw()`) as variveis globais são visíveis por qualquer parte do código, podendo inclusive ser em qualquer parte alteradas.

### exemplo de uma variável global

```pde
int x;  //x é uma variável global

void setup(){
  size(200, 200);
  x = width/2;
}

void draw(){
   background(0);
   ellipse(x, 100, 10, 10);
   x = x + 1;
   if (x > width) {
     x = 0;
   }
}
```

É comum escutarmos que devemos usar variáveis globais com parcimônia, usadas descuidadamente, elas criam o risco de alterarmos  inadvertidamente valores em pontos inesperados do programa.
