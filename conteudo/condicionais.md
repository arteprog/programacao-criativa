# Condicionais

## As bifurcações no caminho de execução do código

*Se* está chovendo (a condição de chuva é verdadeira) *então* eu levo meu guarda-chuva.

Opcionalmente, *senão* (se a condição de chuva é falsa), uma outra ação é tomada: eu levo meus óculos de sol.

## Sintaxe if/else e if

![condicional](/assets/imagens/condicional-com-else.jpg)

``` java
if (chovendo) {        // a condição 'chovendo' é avaliada como verdadeira ou falsa
  levarGuardaChuva();  // Se verdadeira a condição, então... bloco de código a ser executado;
} else {               // termina o “então” e opcionalmente começa o “senão”
  levarOculos();       // Bloco opcional de código a ser executado se a condição for falsa;
}                      // termina o bloco do “senão”, continua o passeio.
```

![condicional](/assets/imagens/condicional-sem-else.jpg)

``` java
if (chovendo) {        // a condição 'chovendo' é avaliada como verdadeira ou falsa
  levarGuardaChuva();  // Se verdadeira a condição, então... bloco de código a ser executado;
}                      // termina o bloco do “se/então”, continua o passeio.
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

Os valores *true* (verdadeiro) e *false* (falso) são do tipo *boolean* (Booleanos, em homenagem a [George Boole](https://pt.wikipedia.org/wiki/George_Boole)), podem ser acessados por meio de variáveis de sistema (como *mousePressed*) e são também o resultado de uma série de operações de comparação assim como as chamadas operações lógicas E (&&), OU (||) e NÃO (

|operador | uso | descrição |
|---  |---- |--- |
| > | e1 > e2 |  verdadeiro se *e1* maior que *e2* |
| >= | e1 >= e2 | 
| < | e1 < e2 |
| <= | e1 <= e2 |
| == | e1 == e2 |
| != | e1 != e2 |
| && | e1 && e2 |
| \|\| | e1 \|\| e2 | verrdadeiro se *e1* OU *e2* for verdadeiro |
| ! | !e1 | se *e1* for verdadeiro, avalia falso e vice-versa |

## Bibliografia

Casey Reas and Ben Fry. 2007. Processing: A Programming Handbook for Visual Designers and Artists. Cambridge: MIT Press.
