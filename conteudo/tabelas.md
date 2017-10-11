# Exemplo de como importar dados de uma tabela
 
 CSV significa ‘Comma Separated Values’, valores separados por vírgulas. 
 TSV ou ‘.tab’ são arquivos com dados separados por caracteres de tabulação. 
 Existe uma estrutura especial chamada `Table` que facilita manipular dados em forma de tabela no Processing.

## Sintaxe

Dada um objeto do tipo `Table` chamada `tabela`, podemos ler uma célula:
 ```java
 int valor1 = tabela.getInt(número da linha, número da coluna);
 float valor 2 = tabela.getFloat(número da linha, número da coluna);
 String valor3 = tabela.getString(número da linha, número da coluna);
 ```
### para ler uma linha da tabela:
```java
TableRow linha = tabela.getRow(3) // lê a quarta linha
\\ Depois de ler uma linha, nós podemos pedir por uma valor específico de uma coluna
 int x = linha.getInt("nome da coluna");
```

# Exemplo

Como carregar dados de um arquivo CSV externo numa variável do tipo Table

```java
Table tabela; // Declarar uma variável do tipo Table
String  URL =
  "https://docs.google.com/spreadsheets/d/1cdwfpjI9OEM1_Cd4djzdMqBiu82Q36eMSJLDLR9cz24/pub?gid=0&single=true&output=csv"; 
Bolinha[] bolinhas;
int numLinhas;

void setup() {
  size(600, 600);
  tabela = loadTable(URL, "header, csv");
  //Para importar tabelas armazenadas na pasta DATA, use a sintaxe abaixo:
  //tabela = loadTable("data.csv", "header");
  numLinhas = tabela.getRowCount();
  bolinhas = new Bolinha[numLinhas];
  for (int i=0; i < numLinhas; i++) {
    TableRow linha = tabela.getRow(i);
    float x = linha.getFloat("x");
    float y = linha.getFloat("y");
    float tamanho = linha.getFloat("tamanho");
    int R = linha.getInt("R");
    int G = linha.getInt("G");
    int B = linha.getInt("B");
    int v = linha.getInt("v");
    bolinhas[i] = new Bolinha(x, y, tamanho, R, G, B, v);
  }
}

void draw() {
  for (int i = 0; i < numLinhas; i++) {
    bolinhas[i].desenhar();
  }
}

class Bolinha {
  float x, y, v;
  float tamanho;
  int R, G, B;

  Bolinha(float x_, float y_, float tamanho_, 
          int R_, int G_, int B_, int v_) {
    x = x_;
    y = y_;
    tamanho = tamanho_;
    R = R_;
    G = G_;
    B = B_;
    v = v_;
  }
  
  void desenhar() {
    fill(R, G, B);
    ellipse(x, y, tamanho, tamanho);
}
```
