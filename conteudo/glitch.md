# Glitch art

Prática de criar/usar erros digitais ou analógicos para fins estéticos, seja por corromper dados digitais ou manipulando fisicamente dispositivos eletrônicos.

Gaulon diz “O glitch digital [...] é uma forma de ver o código por trás de um documento.” E: “Quando um glitch acontece, não é a imagem, o som ou o vídeo que é transformado, mas sim seu código binário.” - Benjamin Gaulon, “Benjamin Gaulon AKA Recyclism” (IdN, 18(3), 2011), 37.


### Como ler e escrever bytes em um arquivo

```pde
// Para abrir um arquivo e ler seus dados use loadBytes() 
byte b[] = loadBytes("arquivo.jpg");  // b[] é um array de bytes

// Para escrever dados em um arquivo useBytes()
byte[] dados = { 0, 34, 5, 127, 52};
saveBytes("outro_arquivo.dat", dados); // (nome do arquivo com extensão, array de dados)                                 
```

### Exemplo

```pde
// Para criar imagem com glitch a partir de 
// arquivo flor.jpg na sub-pasta /data 

PImage flor;

void setup() {
  fullScreen();
  imageMode(CENTER);
}

void draw() {
  byte[] data=loadBytes("flor.jpg");    // carrega a imagem original

  int loc=(int)random(1, data.length);  // sorteia uma posição no array
  data[loc]=(byte)random(255);          // sorteia um valor de byte e substitui

  saveBytes("flor1.jpg", data);         // salva um novo arquivo modificado
  flor = loadImage("flor1.jpg");        // carrega a imagem modificada
  image (flor, width/2, height/2, 600, 370);
}
```
