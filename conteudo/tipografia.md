# Tipografia

## Trabalhando com fontes e texto no Processing

Usamos `text("Lorem Ipsum dolor", x, y)` para escrever um texto na área de desenho.

O tamanho pode ser controlado, em pontos, por `textSize()`. O alinhamento pode ser alterado por `textAlign()`. A cor vem do `fill()`.

### Exemplo básico

```pde
/* Adaptado do tutorial
   https://processing.org/tutorials/typography/ */

float x = 33;
float y = 60;

void setup() {
  size(100, 100);
  textSize(12);
  textAlign(CENTER, BOTTOM); // pode ser usado LEFT, RIGHT no primeiro parâmetro e CENTER ou TOP no segundo
  noStroke();
}

void draw() {
  fill(204, 120);
  rect(0, 0, width, height);
  fill(0);
  // Se o mouse estiver sobre o texto, mova!
  if ((mouseX >= x) && (mouseX <= x+55) &&
    (mouseY >= y-24) && (mouseY <= y)) {
    x += random(-2, 2);
    y += random(-2, 2);
  }
  text("Cócegas", x, y);
}
```

## Definindo a fonte

Se não indicarmos uma fonte, uma padrão será usada, mas podemos criar uma nova fonte e usar com uma variável `PFont` em `textFont()`, a partir de uma fonte já instalada ou de um arquivo vetorial **.ttf** ou **.otf** na pasta **/data** :

```pde
printArray(PFont.list());
f = createFont("Bitstream Vera Sans Mono Bold", 24);
textFont(f);
```

Especialmente no caso de não termos permissão para distribuir o arquivo vetorial da fonte, podemos criar uma fonte bitmap a partir da original e distribuir este novo arquivo **.vlw***, na pasta **/data**. Usando a ferramenta **Tool > Create Font...** produzimos o arquivo da fonte que pode ser carregado numa variável `PFont` da seguinte maneira:

```pde
font = loadFont("LetterGothicStd-32.vlw");
```

## Uma grade de letras, símbolos, glifos!

Copie o arquivo descompactado **.otf*** da fonte [Garoa Hacker Clube Bold](https://garoa.net.br/wiki/Fonte_Garoa_Hacker_Clube_Bold) na sub-pasta **/data** do seu sketch.

```pde
PFont f;
String meuString = "ABCDEFGHIJKLMNOPQRSTUVWXYZ☂#$*&";
int numLetras = meuString.length(); 
int passo = 25;

void setup() {
  size(640, 360);
  background(0);
  printArray(PFont.list());     // lista de fontes instaladas no computador
  // "Descomente" as duas linhas abaixo caso tenha copiado a fonte na pasta /data
  // f = createFont("GaroaHackerClubeBold.otf", 24); 
  // textFont(f);
  textAlign(CENTER, CENTER); // Alinhamento horizontal e vertical
  textSize(24);             // Tamanho do texto
  noLoop();  // Este exemplo desliga a repetiçao do draw()...
}

void draw() {
  background(0);
  for (int y = 12; y <= height-12; y += passo) {
    for (int x = 12; x <= width-12; x += passo) {
      int sorteio = int(random(numLetras));
      char umChar = meuString.charAt(sorteio);
      if (umChar == 'A' || umChar == 'E' || umChar == 'I'
        || umChar == 'O' || umChar == 'U') {
        fill(255, 204, 0);
      } else {
        fill(255);
      }
      // Desenha a letra na tela
      text(umChar, x, y);
    }
  }
}

void mousePressed() {
  loop();
}

void mouseReleased() {
  noLoop();
}
```

## Bibliografia

REAS, C.; FRY, B. Processing: a programming handbook for visual designers and artists. Cambridge, Mass: MIT Press, 2007. 
