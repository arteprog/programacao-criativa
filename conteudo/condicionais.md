# Condicionais

## As bifurcações no caminho de execução do código

Saindo de casa, se (`if`) está chovendo, a condição "chovendo" é verdadeira (`true`), então levo o guarda-chuva;

opcionalmente defino que, senão (`else`), quando a condição "chovendo" é falsa (`false`), levo óculos de sol.

## Sintaxe if/else e if

![condicional](/programacao-criativa/assets/imagens/condicional-com-else.jpg)

``` java
if (chovendo) {        // a condição "chovendo" é avaliada como true (verdadeiro) ou false (falso)
  levarGuardaChuva();  // se verdadeira a condição, então este bloco de código será executado
} else {               // termina o “se/então” e começa o “senão”
  levarOculos();       // este bloco será executado apenas quando "chovendo" é falso
}                      // termina o bloco do “senão”, continua o passeio.
```

![condicional](/programacao-criativa/assets/imagens/condicional-sem-else.jpg)

``` java
if (chovendo) {        // a condição "chovendo" é avaliada como true (verdadeiro) ou false (falso)
  levarGuardaChuva();  // se verdadeira a condição, então este bloco de código será executado
}                      // termina o bloco do “se/então”, continua o passeio.
```

## Exemplos

![exemplo1](/programacao-criativa/assets/imagens/condicional1.png)

``` pde
void setup(){
  size(200, 200);
}

void draw(){
  if (mouseY<100) { // se a posição Y do mouse for menor que 100, o mouse estiver perto do topo da tela
    fill(255);      // então pede preenchimento branco (só executa quando mouseY é menor que 100)
  } else {          // termina o bloco “se/então” e começa o do “senão”
    fill(100);      // preenchimento cinza 100 (só executa quando mouseY não é menor que 100)
  }                 // termina o bloco do “senão”    

  if (mousePressed) {                 // Se o mouse estiver pressionado
     ellipse(mouseX, mouseY, 10, 10); // Então desenha um círculo na posição do mouse
  }                                   // termina o bloco (repare que não faz nada se o mouse estiver solto)

  if (keyPressed && key == 'a') { // Se uma tecla foi precionada E (&&) a tecla foi o caractere 'a'
    background(200);              // Apague a tela com um fundo cinza (só executa sob as condições acima)
  }
}
```

## Comparações e operadores lógicos

Os valores `true` (verdadeiro) e `false` (falso) são o resultado das comparações e das chamadas operações lógicas **e** (`&&`), **ou** (`||`) e **não** (`!`). Podem ser armazenados em variáveis do tipo *boolean* (Booleano, em homenagem a [George Boole](https://pt.wikipedia.org/wiki/George_Boole)) definidas pela pessoa que criou o programa, representando um *estado*.

Da mesma forma, são os valores acessados quando usamos as variáveis de sistema *mousePressed* e *keyPressed*.
 
|operador | uso | descrição |
|:---:  |:---: |--- |
| `>` | `e1 > e2` |  verdadeiro se *e1* **maior** que *e2* |
| `>=` | `e1 >= e2` | verdadeiro se *e1* **maior ou igual** a *e2* |
| `<` | `e1 < e2` | verdadeiro se *e1* **menor** que *e2* |
| `<=` | `e1 <= e2` | verdadeiro se *e1* **menor ou igual** a *e2* |
| `==` | `e1 == e2` | verdadeiro se *e1* **igual** a *e2* |
| `!=` | `e1 != e2` | verdadeiro se *e1* **diferente** de *e2* |
| `&&` | `e1 && e2` | verdadeiro se *e1* **e** *e2* forem ambos verdadeiros |
| `\|\|` | `e1 \|\| e2` | verrdadeiro se *e1* **ou** *e2* forem verdadeiros |
| `!` | `!e1` | **não** *e1* verdadeiro resulta falso, e **não** *e1* falso resulta verdadeiro |

## Condicionais aninhadas e outras estruturas

É comum encontraramos, além da composição das condições usando operadores lógicos, `ìf` dentro de um `ìf` ou de um `else`.

No caso de repetidos `if \ else if` podemos usar a estrutura [`switch\case`](https://processing.org/reference/switch.html)

Confira também a abreviação de `if` + atribuições, o [operador ternário `?:`](https://processing.org/reference/conditional.html)

## Bibliografia

REAS, C.; FRY, B. Processing: a programming handbook for visual designers and artists. Cambridge, Mass: MIT Press, 2007. 

TERZIDIS, K. Algorithms for Visual Design Using the Processing Language. [s.l.] John Wiley & Sons, 2009. 

