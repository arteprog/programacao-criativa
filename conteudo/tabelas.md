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
Table tabela;
String  URL = "https://raw.githubusercontent.com/arteprog/programacao-criativa/master/assets/data/tabela.csv";

void setup() {
  size(200, 200);
  tabela = loadTable(URL, "header, csv");
  println(tabela.getRowCount() + " linhas na tabela"); 
  for (TableRow row : tabela.rows()) {
    float x = row.getFloat("x");
    float y = row.getFloat("y");
    float tamanho = row.getFloat("tamanho");
    int R = row.getInt("R");
    int G = row.getInt("G");
    int B = row.getInt("B");
    fill(R, G, B);
    ellipse(x, y, tamanho, tamanho);
  }
}
```
