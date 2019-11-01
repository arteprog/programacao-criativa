# Exportação

### Como exportar uma imagem (bitmap/raster)

```pde
// Para exportar um PNG (na pasta do sketch) digite 's'

void setup() {
  size(400, 400);
}

void draw() {
  // aqui vai o seu desenho
  rect(100, 100, 200, 100);
}

void keyPressed() {
  if (key == 's') {
    saveFrame("imagem.png"); // salva um arquivo .PNG
  }
}
```

### Como exportar um PDF

```pde
// Para exportar um PDF (na pasta do sketch) digite 'p'
import processing.pdf.*;

boolean salvarPDF = false;

void setup() {
  size(400, 400);
}

void draw() {
  // inicio da gravação do PDF
  if (salvarPDF) {
    beginRecord(PDF, "saida.pdf");
  }
  // aqui vai o seu desenho
  rect(100, 100, 200, 100);

  // fim da gravação do PDF
  if (salvarPDF) {
    endRecord();
    print("PDF salvo");
    salvarPDF = false;
  }
}

void keyPressed() {
  if (key == 'p') {
    salvarPDF = true;
  }
}

```

