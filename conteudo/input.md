# Input

## Entradas de dados

No Processing, o teclado e o mouse são as principais formas de entrada de dados. Posteriormente trataresmos da leitura de arquivos e outras fontes de dados.

Há duas maneiras de se obter informações sobre cliques do mouse e teclas sendo pressionadas. Variáveis de sistema como `keyPressed`, `keyReleased`, `mousePressed` e `mousePressed` ou funções definidas pela pessoa criando o programa com os nomes "encomendados", como `keyPressed()`, `keyReleased()`, `mousePressed()`ou `mouseReleased()`. Neste último caso, atente que é preciso que exista um bloco `draw()`, mesmo que vazio, para que os eventos de teclado e mouse disparem as funções.

## Vocabulário

Mouse

```
mouseButton     // variável de sistema que indica qual botão do mouse foi clicado LEFT, RIGHT ou CENTER
mouseClicked(   // defina uma função com este nome para ser executada quando o mouse é clicado (já solto o botão)
mouseDragged()  // defina uma função com este nome para ser executada quando o mouse é movido pressionado
mouseMoved()    // defina uma função com este nome para ser executada quando o mouse é movido
mousePressed()  // defina uma função com este nome para ser executada quando o botão do mouse é pressionado
mousePressed    // variável de sistema que indica o estado do mouse (true indica pressionado)
mouseReleased() // defina uma função com este nome para ser executada quando o botão do mouse é solto depois de pressionado
mouseWheel()    // defina uma função com este nome para ser executada quando a rodinha do mouse é girada
mouseX          // variável de sistema que contém a posição X do mouse na tela 
mouseY          // variável de sistema que contém a posição Y do mouse na tela
pmouseX         // variável de sistema que contém a posição X anterior do mouse na tela
pmouseY         // variável de sistema que contém a posição Y anterior do mouse na tela
```

Keyboard

```
key           // caractere da última tecla alfa-numérica pressionada
keyCode       // código da última tecla, usado para identificar teclas não alfa-numéricas, como SHIFT, UP e etc.
keyPressed()  // defina uma função com este nome para ser executada quando uma tecla é pressionada
keyPressed    // variável de sistema que indica se alguma tecla está pressionada
keyReleased() // defina uma função com este nome para ser executada quando uma tecla é solta
keyTyped()    // defina uma função com este nome para ser executada quando uma tecla alfa-numérica é digitada
```

## Exemplo

<!-- [exemplo1](/assets/imagens/condicional1.png) -->

``` pde
void setup(){
  size(200, 200);
}

void draw(){
  if (mousePressed) {                      // Se o mouse estiver pressionado
     line(pmouseX, pmouseY, mouseX, mouseY); // Então desenha uma linha da posição anterior do mouse até a atual
  }                                        // termina o bloco (repare que no faz nada se o mouse estiver solto)
}

void keyPressed(){    // Esta funço executa uma vez quando uma tecla é pressionada
  if (key == 'a') {   // Se a tecla do caractere 'a' foi a última pressionada
    background(200);  // Apague a tela com um fundo cinza (só executa sob as condições acima)
  }
}
```


## Bibliografia

REAS, C.; FRY, B. Processing: a programming handbook for visual designers and artists. Cambridge, Mass: MIT Press, 2007.
