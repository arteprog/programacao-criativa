# Desenho Básico

## Atividade 01
1. Desenhe no centro do papel a letra a;

2. Agora vamos usar um papel quadriculado. Cada quadrado será representado por um número.

![a](https://lh4.googleusercontent.com/bgzgCX82iGyXke7z_kd_N6dlZULrmeDuuTLkTKTRIc2SDDaem-l1ksiehYLUZXWzIjnN9MYA33YkmVk=w1267-h627)

> 1, 3, 1

> 4, 1

> 1, 4

> 0, 1, 3, 1

> 0, 1, 3, 1

> 1, 4

"Escrever em uma linguagem humana permite ao autor utilizar a ambiguidade das palavras e ter uma grande flexibilidade na construção de frases. Essas técnicas permitem múltiplas interpretações de um único texto e dão a cada autor uma voz única. Cada programa de computador também revela o estilo de seu autor, mas há muito menos espaço para a ambiguidade."(Casey e McWilliams 2010).

## Coordenadas

O computador precisa saber a posição de cada ponto que desenha. Para fazer isso, normalmente usamos coordenadas cartesianas: um eixo x corre da esquerda para a direita, e o eixo y vai de cima para baixo. Esses eixos nos permitem especificar uma posição precisa na grade usando um par de números, normalmente o valor x seguido pelo valor y. Por exemplo, um ponto em (5, 14) é 5 linhas a partir da borda esquerda da tela e 14 linhas para baixo do topo.

![coor](https://lh4.googleusercontent.com/3h-CHADOSE3UxUoInnlaclsdaojVzfdyloCy1UKfYu_SPKKKp0msuW3LzZCH70x-ok5jcgwqhpEE8Hw=w1267-h627-rw)

## Tamanho
```java
size(600, 400); // tamanho da tela size(largura, altura) 
println(width); // escreve no console largura atual da tela
println(height); // escreve no console altura atual da tela
``` 

## Formas

>Ponto é o que não tem partes, não tem grandeza alguma. Linha é o comprimento sem largura. Superfície é o que tem comprimento e largura. As extremidades da linha são pontos. As extremidades da superfície são linhas. (Euclides c. 300 AC)

>A linha é o rastro deixado pelo ponto em movimento. (Wassily Kandinsky 1866-1944)

```java
rect(20, 10, 40, 80); // retângulo rect(x, y, largura, altura)
ellipse(10, 20, 50, 50); // oval, ellipse(x, y, largura, altura)
line(10,10, 50,50); // linha line(x1, y1, x2, y2)
point(100, 50); // ponto point(x, y)
```

## Cor
```java
fill(255, 0, 0, 100); // preenchimento vermelho (R:Vermelho, G:Verde, B:Azul, Alpha:Transparência)
noFill(); // sem preenchimento, formas vazadas
stroke(0, 0, 255); // exemplo de cor do contorno azul cor(R, G, B)
strokeWeight(10); // espessura do contorno
noStroke(); // sem contorno
```

## Fundo
```java
background(0, 255, 0) // fundo verde, limpa a tela background(R, G, B)
```

## Comentários
```java
/* Comentários são anotações do código, não são executados, e quando começam com barra-e-asterisco
podem ter várias linhas e terminam com asterisco-e-barra */

// Comentários de uma linha só começam com duas barras. São um jeito rápido de desativar uma linha!
```

## Bibliografia

Reas, Casey e McWilliams. 2010. FORM+CODE in design, art and architecture. New York: Princeton Architectural Press.
