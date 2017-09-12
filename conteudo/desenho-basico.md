# Desenho Básico

## Coordenadas

## Tamanho
```java
size(600, 400); // tamanho da tela size(largura, altura) 
println(width); // escreve no console largura atual da tela
println(height); // escreve no console altura atual da tela
``` 

## Formas
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
/* Comentários são anotações do código, não são executados, e quando começam com barra-e-asterisco podem ter várias linhas 
e terminam com asterisco-e-barra */

// Comentários de uma linha só começam com duas barras. São um jeito rápido de desativar uma linha!

