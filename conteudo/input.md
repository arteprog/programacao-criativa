# Input

## Entradas de dados

## Exemplos

![exemplo1](/assets/imagens/condicional1.png)

``` pde
void setup(){
  size(200, 200);
}

void draw(){
  if (mousePressed) {                 // Se o mouse estiver pressionado
     ellipse(mouseX, mouseY, 10, 10); // Então desenha um círculo na posição do mouse
  }                                   // termina o bloco (repare que no faz nada se o mouse estiver solto)
}


void keyPressed(){    // Esta funço executa uma vez quando uma tecla é pressionada
  if (key == 'a') {   // Se a tecla do caractere 'a' foi a última pressionada
    background(200);  // Apague a tela com um fundo cinza (só executa sob as condições acima)
  }
}
```

## Mais vocabulário

Mouse

```
mouseButton
mouseClicked()
mouseDragged()
mouseMoved()
mousePressed()
mousePressed
mouseReleased()
mouseWheel()
mouseX
mouseY
pmouseX
pmouseY
```

Keyboard

```
key
keyCode
keyPressed()
keyPressed
keyReleased()
keyTyped()
```

Files

```
BufferedReader
createInput()
createReader()
launch()
loadBytes()
loadJSONArray()
loadJSONObject()
loadStrings()
loadTable()
loadXML()
parseJSONArray()
parseJSONObject()
parseXML()
selectFolder()
selectInput()
```

Time & Date

```
day()
hour()
millis()
minute()
month()
second()
year()
```

## Bibliografia

REAS, C.; FRY, B. Processing: a programming handbook for visual designers and artists. Cambridge, Mass: MIT Press, 2007.
