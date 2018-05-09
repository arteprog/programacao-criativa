# Declarando e chamando funções

### Sintaxe da definição/declaração
```java
tipo nome_da_função(tipo parâmetro, tipo outro_parâmetro) {
   Bloco de código que a função executa;
} 
```

### Sintaxe do uso/invocação da função
```java
nome_da_função(valor_parâmetro, valor_outro_parâmetro);
// esta função precisa de dois parâmetros
```

### Exemplo da função `olho()`

```pde
void setup() {
  size(400, 400);
}

void draw() {
  background(0);
  olho(300, 100, random(50, 100));
  olho(100, 200, random(10, 150)); 
  olho(200, 300, random(10, 150));
}

void olho(float x, float y, float tamanho) {
  noStroke();
  fill(255);
  ellipse(x, y, tamanho, tamanho/2);
  fill(0);
  ellipse(x, y, tamanho*.40, tamanho*.40);
}
```
