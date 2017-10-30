# Tipografia

## Trabalhando com fontes e texto no Processing

Usamos `text("loren ipso", x, y)` para escrever um texto na área de desenho. O tamanho pode ser controlado, em pontos por `textSize()`.

## Exemplos

```pde
/* Adaptado do tutorial
   https://processing.org/tutorials/typography/ */

float x = 33;
float y = 60;

void setup() {
  size(100, 100);
  textSize(12);
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

Se não indicarmos uma fonte, uma padrão será usada, mas podemos carregar em uma `PFont` para usar em `textFont()` uma fonte já instalada:

```pde
printArray(PFont.list());
f = createFont("Bitstream Vera Sans Mono Bold", 24);
textFont(f);
```
Podemos criar uma PFont a partir de uma fonte vetorial **.ttf** ou** .otf** na pasta **/data**

```pde


```

Ou ainda, podemos criar uma fonte bitmap a partir de uma fonte vetorial e a partir dela carregar uma PFont, usando a ferramenta **Tool > Create Font...**

## Exemplo 2

```pde
/* Uma grade de letras, símbolos, glifos! */

PFont f;
String meuString = "ABCDEFGHIJKLMNOPQRSTUVWXYZ#$*&";

void setup() {
  size(640, 360);
  background(0);
  printArray(PFont.list());     // lista de fontes instaladas no computador
  // f = createFont("Bitstream Vera Sans Mono Bold", 24);  // cria uma fonte Pfont
  // textFont(f);                // Indica a fonte que vai ser usada
  textAlign(CENTER, CENTER); // Alinhamento horizontal e vertical
  textSize(24);             // Tamanho do texto
  noLoop();  // Este exemplo para a repetiçao do draw()...
}

void draw() {
  background(0);
  int passo = 25;
  for (int y = 12; y <= height-12; y += passo) {
	for (int x = 12; x <= width-12; x += passo) {
  	int sorteio = int(random(30));
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

```



## Bibliografia

REAS, C.; FRY, B. Processing: a programming handbook for visual designers and artists. Cambridge, Mass: MIT Press, 2007. 
