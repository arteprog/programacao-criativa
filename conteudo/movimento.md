# Movimento

## Bounce

```pde
int raio = 50; // tamanho da altura/largura da ellipse
float pX, pY; //posição inicial X e Y;   

float vX = random(-4, 4);  // Velocidade X inicial
float vY = random(-4, 4);  // Velocidade Y inicial

void setup() {
  size(640, 360);
  noStroke();
  frameRate(30);
  // ellipseMode (RADIUS) também usa os dois primeiros parâmetros da elipse () 
  // como o ponto central da forma, mas usa o terceiro e quarto parâmetros para
  // especificar a metade da largura e altura das formas.
  ellipseMode(RADIUS);
  // Definir posições iniciais
  pX = width/2;
  pY = height/2;
}

void draw() {
  background(255);

  // Atualizar a posição da ellipse
  pX = pX + vX ;
  pY = pY + vY ;

  // Testar se a ellipse está fora da tela
  // Se estiver, inverter a velocidade multiplicando por -1.
  if (pX > width-raio || pX < raio) {
    vX = -vX;
  }
  if (pY > height-raio || pY < raio) {
    vY = -vY;
  }

  // Desenhar a ellipse
  fill(0); // preenchimento preto
  noStroke(); // sem contorno
  ellipse(pX, pY, raio, raio);
}
```

![](https://github.com/arteprog/programacao-criativa/blob/master/assets/imagens/bounce.gif?raw=true)

