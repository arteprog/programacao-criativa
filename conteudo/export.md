# Exportação

### Como exportar uma imagem (bitmap/raster)

A forma mais simples de exportação de uma imagem na área de desenho.

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

Neste exemplo é salvo o que for desenhado em um único frame.
Veja o exemplo de exportação de SVG mais abaixo se quiser escalar o arquivo exportado.
No caso do PDF é possível ainda produzir um arquivo com múltiplas páginas.

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

### Como exportar um SVG, permitindo escolher o local do arquivo

O exemplo a seguir é parcido com o da exportação de PDF, mas acrescenta uma janela de diálogo que permite a pessoa escolher onde quer salvar o arquivo. Essa estratégia pode ser usada para salvar qualquer tipo de arquivo, e usando funções *call back* semelhantes é possível escolher arquivos para leitura também.

```pde
import processing.svg.*;

boolean saveFrame = false;
PGraphics output;
float fatorEscala = 3;

void setup() {
  size(400, 400);
}

void draw() {
  if (saveFrame) {
    beginRecord(output);
    output.scale(fatorEscala);
  }
 
  // Desenho aqui
  background(200, 255, 255);
  rect(100, 100, 100, 100);

  if (saveFrame) {
    endRecord();
    saveFrame = false;
  }
}

void salvaSVG(File selection) {
   if (selection == null) {
    println("Salvar cancelado.");
  } else {
    println("Salvando em: " + selection.getAbsolutePath());
    output =  createGraphics(int(width * fatorEscala),
                                int(height * fatorEscala),
                                SVG, selection.getAbsolutePath());
    saveFrame = true;
  }
}

void keyPressed() {
  if (key == 's') {
    File sugestao = new File("exemplo.svg");
    selectOutput("Salvar:", "salvaSVG", sugestao);
  }
}
```
