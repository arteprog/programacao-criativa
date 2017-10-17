# Pixels e imagens

Uma imagem digital, por vezes chamada de uma imagem bitmap, nada mais é do que uma sequência de números indicando variações de vermelho, verde e azul numa localização particular de uma grade de ***pixels(**, um neologismo cunhado na década de 60 juntado *pix*, abreviação de *picture*, e *el* de *element*, o menor elemento de uma imagem.

A maior parte do tempo nós visualizamos esses pixels como retângulos miniatura justapostos na tela do computador. No entanto, com um pouco de pensamento criativo e com a manipulação dos pixels com código, podemos mostrar esta informação de inúmeras maneiras. Apesar disso, de tempos em tempos, podemos querer quebrar nossa rotina de desenho corriqueira e manipular os pixels da tela diretamente. O Processing proporciona isso através de um **array** de pixels.

Estamos acostumados com a ideia de cada pixel na tela ter uma posição X e Y numa janela. No entanto, um array de pixels tem apenas uma dimensão, armazenado os valores de cor numa sequência linear.
    
Como os pixels aparecem:

| 0 | 1 | 2 | 3 | 4 |
| --- | --- | --- | --- | --- |
| **5** | **6** | **7** | **8** | **9** |
| **10** | **11** | **12** | **13** | **14** |
| **15** | **16** | **17** | **18** | **19** |
| **20** |
21
22
23
24


Como os pixels são armazenados:
0
1
2
3
4
5
6
7
8
9
.
.
.






Imagens são armazenadas na memória como uma sequeê

```pde
PImage img;  // Declarando uma variável do tipo PImage

void setup() {
  size(640, 360);
  noStroke();
  img = loadImage("moonwalk.jpg");   // carregando uma imagem da pasta /data/
}

void draw() {
  image(img, 0, 0);  // desenha a imagem (PImage, x, y, [largura, altura]*)  *opcionais 
  color cor = img.get(mouseX, mouseY); // pega a cor do pixel na posição x, y
  fill(cor);                          // pede o preenchimento!
  ellipse(mouseX, mouseY, 100, 100); // desenha um círculo
}

// Para criar um novo objeto PImage (tipo de dados para armazenar imagens) vazio, fornecendo um buffer de pixels para manipular use createImage().
createImage(w, h, formato) // w (largura em pixels), h (altura em pixels),
       // formato (RGB, ARGB ou ALPHA: canal alpha em escala de cinzas)    

loadPixels()  // dá acesso a um array contendo os pixels da imagem

updatePixels() // atualiza na imagem modificações feitas no array
```
