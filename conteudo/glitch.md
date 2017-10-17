# Glitch art

Prática de criar/usar erros digitais ou analógicos para fins estéticos, seja por corromper dados digitais ou manipulando fisicamente dispositivos eletrônicos.

Gaulon diz “O glitch digital [...] é uma forma de ver o código por trás de um documento.” E: “Quando um glitch acontece, não é a imagem, o som ou o vídeo que é transformado, mas sim seu código binário.” - Benjamin Gaulon, “Benjamin Gaulon AKA Recyclism” (IdN, 18(3), 2011), 37.


### Como ler e escrever bytes em um arquivo

```pde
loadBytes() // Abre um arquivo e lê os seus dados binários 
byte b[] = loadBytes("arquivo.jpg");

byte[] dados = { 0, 34, 5, 127, 52};
saveBytes("outro_arquivo.dat", dados); // Escreve os dados no arquivo
                             // (arquivo com extensão, array de dados)    
```

### Exemplo

```pde
PImage flor;

void setup() {
  fullScreen();
  imageMode(CENTER);
}

void draw() {
  byte[] data=loadBytes("flor.jpg");

  int loc=(int)random(1, data.length);
  data[loc]=(byte)random(255);

  saveBytes("flor1.jpg", data);
  flor = loadImage("flor1.jpg");
  image (flor, width/2, height/2, 600, 370);
}
```
