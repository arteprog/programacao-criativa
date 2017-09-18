# Condicionais

## As bifurcações no caminho de execução do código

*Se* está chovendo (a condição de chuva é verdadeira) *então* eu levo meu guarda-chuva.
(opcionalmente, *senão* (se a condição de chuva é falsa) eu levo meus óculos de sol)

## Sintaxe if/else

```java
 if (condição) {  // a condição é avaliada como verdadeira ou falsa
                 // Se verdadera, então... bloco de código a ser executado;
 } else {         // termina o “Então” e opcionalmente começa o “Senão”
                 // Bloco opcional de código a ser executado se a condição for falsa;
 }                // termina o bloco do “Senão”    
 
``` 

## Exemplos

```pde
void setup(){
  size(500, 500);
}

void draw(){
  if (mousePressed) {                    // “SE” a o mouse estiver pressionado
     ellipse(mouseX, mouseY, 40, 40);    // ENTÃO desenha um círculo na posição do mouse
  }                                      // termina o “SE”

  if (mouseY<100) { // SE a posição Y do mouse menor que 100 (perto do topo da tela)
    fill(255);      // ENTÃO preenchimento branco
  } else {          // termina o “SE” e começa o “SENÃO”
    fill(100);      // preenchimento cinza 100
  }                 // termina o “SENÃO”    

  if (keyPressed && key == 'a') {
    background(128);
  }
}
```

## Bibliografia

Casey Reas and Ben Fry. 2007. Processing: A Programming Handbook for Visual Designers and Artists.Cambridge: MIT Press.
