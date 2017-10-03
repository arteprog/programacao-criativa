/* Versão do código da casa que soma a posição nas coordenadas dos objetos. */

void house(int x, int y)
{
  triangle(x + 15, y, x, y + 15, x + 30, y + 15);
  rect(x, y + 15, 30, 30);
  rect(x + 12, y + 30, 10, 15);
}


/*Compare com esta versão que usa o translate(). Neste caso o código desenha a casa sempre no mesmo lugar, no ponto (0, 0), e deixa a translação fazer o trabalho! */

void house(int x, int y) 
{
  pushMatrix();
  translate(x, y);
  triangle(15, 0, 0, 15, 30, 15);
  rect(0, 15, 30, 30);
  rect(12, 30, 10, 15);
  popMatrix();
}
