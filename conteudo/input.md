# Input - entradas de dados

No Processing, o teclado e o mouse são as principais formas de entrada de dados. Posteriormente trataresmos da leitura de arquivos e outras fontes de dados. Há duas maneiras de se obter informações sobre o movimento e cliques do mouse, assim como saber sobre as teclas sendo pressionadas no teclado. 

1. Variáveis de sistema 

As variáveis de sistema como `mouseX`, `mouseY`, `keyPressed`e `mousePressed` contém a todo instante informações sobre o estado do teclado e mouse. Podem ser consultadas em qualquer lugar do programa e são vistas frequentemente em condicionais dentro do bloco de `draw()`.

| tipo | nome | descrição | 
| --- | --- | --- |
| int | mouseButton     |  variável de sistema que indica qual botão do mouse foi clicado LEFT, RIGHT ou CENTER
| boolean | mousePressed    |  variável de sistema que indica o estado do mouse (true indica pressionado)
| int | mouseX          |  variável de sistema que contém a posição X do mouse na tela 
| int | mouseY          |  variável de sistema que contém a posição Y do mouse na tela
| int | pmouseX         |  variável de sistema que contém a posição X anterior do mouse na tela
| int | pmouseY         |  variável de sistema que contém a posição Y anterior do mouse na tela
| char | key           |  caractere da última tecla alfa-numérica pressionada
| int | keyCode       |  código da última tecla, usado para identificar teclas não alfa-numéricas, como SHIFT, UP e etc.
| boolean | keyPressed    |  variável de sistema que indica se alguma tecla está pressionada

### Exemplo

``` pde
void setup(){
  size(200, 200);
}

void draw(){
  if (keyPressed && keyCode == SHIFT) {   // se a tecla SHIFT estiver pressonada
    strokeWeight(5);                      // usa linha mais grossa 
    stroke(255);                          // com traço branco
  } else {                                // senão, quando tecla SHIFT não estiver pressonada
    strokeWeight(1);                      // usa linha fina grossa
    stroke(0);                            // com traço preto
  }

  if (mousePressed) {                        // Se o mouse estiver pressionado
     line(pmouseX, pmouseY, mouseX, mouseY); // Então desenha uma linha da posição anterior do mouse até a atual
  }                                          // termina o bloco (repare que no faz nada se o mouse estiver solto)
}
```

2. Funções para tratar eventos

Definidas pela pessoa criando o programa, com os nomes especiais "encomendados", como `keyPressed()`, `keyReleased()`, `mousePressed()`ou `mouseReleased()`, estas funções precisam ser definidas fora do bloco de `draw()` (note que o `draw()` precisa existir, mesmo que vazio, para garantir a execução de um laço principal do Processing) e serão executadas apenas quando seus respectivos eventos de teclado e mouse acontecerem.

| nome | descrição |
| --- | --- |
| mouseReleased() |  função executada quando o botão do mouse é solto depois de pressionado
| mouseWheel()    |  função executada quando a rodinha do mouse é girada
| mouseClicked()  |  funcão executada quando o mouse é clicado (já solto o botão)
| mouseDragged()  |  função executada quando o mouse é movido pressionado
| mouseMoved()    |  função executada quando o mouse é movido
| mousePressed()  |  função executada quando o botão do mouse é pressionado
| keyPressed()  |  função executada quando uma tecla é pressionada
| keyReleased() |  função executada quando uma tecla é solta
| keyTyped()    |  função executada quando uma tecla alfa-numérica é digitada


### Exemplo

<!-- [exemplo1](/assets/imagens/condicional1.png) -->

``` pde
void setup(){
  size(200, 200);
}

void draw(){
  line(pmouseX, pmouseY, mouseX, mouseY); // Desenha uma linha da posição anterior do mouse até a atual
}

void keyPressed(){              // Esta função executa uma vez quando uma tecla é pressionada
  if (key == 'a') {                           // Se a tecla do caractere 'a' foi a última pressionada
    background(200);                          // Apague a tela com um fundo cinza (só executa sob as condições acima)
  }
  if (keyCode == DOWN) {                      // Se a seta para baixo foi precionada
    saveFrame("imagem-####.png");             // salve a imagem da tela de pintura em um arquivo PNG 
    println("salvo o frame " + frameCount);   // mostre no console o número do frame
  }  
}
```

## Bibliografia

REAS, C.; FRY, B. Processing: a programming handbook for visual designers and artists. Cambridge, Mass: MIT Press, 2007.
