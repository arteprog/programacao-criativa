# Condicionais

## As bifurcações no caminho de execução do código

*Se* está chovendo (a condição de chuva é verdadeira) *então* eu levo meu guarda-chuva.

Opcionalmente, *senão* (se a condição de chuva é falsa), uma outra ação é tomada: eu levo meus óculos de sol.

## Sintaxe if/else e if

![condicional](/assets/imagens/condicional-com-else.jpg)

``` java
if (chovendo) {         // a condição 'chovendo' é avaliada como verdadeira ou falsa
   levarGuardaChuva();  // Se verdadeira a condição, então... bloco de código a ser executado;
} else {                // termina o “então” e opcionalmente começa o “senão”
   levarOculos();       // Bloco opcional de código a ser executado se a condição for falsa;
}                       // termina o bloco do “senão”, continua o passeio.
```

![condicional](/assets/imagens/condicional-sem-else.jpg)

``` java
if (chovendo) {  // a condição 'chovendo' é avaliada como verdadeira ou falsa
                 // Se verdadeira a condição, então... bloco de código a ser executado;
}                // termina o bloco do “se/então”, continua o passeio.
```

## Exemplos

![exemplo1](/assets/imagens/condicional1.png)

``` pde
void setup(){
  size(200, 200);
}

void draw(){
  if (mousePressed) {                 // "Se" o mouse estiver pressionado
     ellipse(mouseX, mouseY, 10, 10); // ENTÃO desenha um círculo na posição do mouse
  }                                   // termina o “Se”

  if (mouseY<100) { // Se a posição Y do mouse menor que 100 (perto do topo da tela)
    fill(255);      // "Então" preenchimento branco
  } else {          // termina o “Então” e começa o “Senão”
    fill(100);      // preenchimento cinza 100
  }                 // termina o “Senão”    

  if (keyPressed && key == 'a') { // Se uma tecla foi precionada E (&&) a tecla foi o caractere 'a'
    background(200);              // Apague a tela com um fundo cinza
  }
}
```
## Os operadores lógicos

| > | op1 > op2 |
| >= | op1 >= op2 |
| < | op1 < op2 |
| <= | op1 <= op2 |
| == | op1 == op2 |
| != | op1 != op2 |
| && | op1 && op2 |
| || | op1 || op2 |

## Bibliografia

Casey Reas and Ben Fry. 2007. Processing: A Programming Handbook for Visual Designers and Artists. Cambridge: MIT Press.
