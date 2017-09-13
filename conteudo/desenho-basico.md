# Desenho Básico

## Atividade 01 - Representação de imagens 

Atividade baseada no projeto [CS Unplugged](http://csunplugged.org/).

1. Desenhe no centro do papel a letra a;

2. Agora vamos usar um papel quadriculado. Cada quadrado será representado por um número.

![a](programacao-criativa/assets/imagens/a.png)

> 1, 3, 1

> 4, 1

> 1, 4

> 0, 1, 3, 1

> 0, 1, 3, 1

> 1, 4

3. Debate

"Escrever em uma linguagem humana permite ao autor utilizar a ambiguidade das palavras e ter uma grande flexibilidade na construção de frases. Essas técnicas permitem múltiplas interpretações de um único texto e dão a cada autor uma voz única. Cada programa de computador também revela o estilo de seu autor, mas há muito menos espaço para a ambiguidade (Casey e Fry 2007).

## Coordenadas

O computador precisa saber a posição de cada ponto que desenha. Para fazer isso, normalmente usamos coordenadas cartesianas: um eixo x corre da esquerda para a direita, e o eixo y vai de cima para baixo. Esses eixos nos permitem especificar uma posição precisa na grade usando um par de números, normalmente o valor x seguido pelo valor y. Por exemplo, um ponto em (5, 14) é 5 linhas a partir da borda esquerda da tela e 14 linhas para baixo do topo.

![coor](programacao-criativa/assets/imagens/coord.jpg)

## Tamanho
```java
size(600, 400); // tamanho da tela size(largura, altura) 
println(width); // escreve no console largura atual da tela
println(height); // escreve no console altura atual da tela
``` 

## Formas

>Ponto é o que não tem partes, não tem grandeza alguma. Linha é o comprimento sem largura. Superfície é o que tem comprimento e largura. As extremidades da linha são pontos. As extremidades da superfície são linhas. (Euclides c. 300 AC)

>A linha é o rastro deixado pelo ponto em movimento. (Wassily Kandinsky 1866-1944)

>No entanto, um ponto é simplesmente um pixel na tela, uma linha é uma seqüência de pixels, e uma forma é uma área de pixels. (Kostas Terzdis 1962- )

```java
rect(20, 10, 40, 80); // retângulo rect(x, y, largura, altura)
ellipse(10, 20, 50, 50); // oval, ellipse(x, y, largura, altura)
line(10,10, 50,50); // linha line(x1, y1, x2, y2)
point(100, 50); // ponto point(x, y)
```

## Atividade 2 

Pesquisar nas [referências do Processing](https://processing.org/reference/), a sintaxe para desenhar os objetos geométricos abaixo:

1. Arco - arc();

2. Curva - curve();

3. Bezier - bezier();

4. Vertex - vertex();

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

Casey Reas and Ben Fry. 2007. Processing: A Programming Handbook for Visual Designers and Artists.Cambridge: MIT Press.
