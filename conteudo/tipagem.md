
# Variáveis, parâmetros e seus tipos

Quando declaramos uma variável (por exemplo `int i = 10;`), `ì` é um nome que vai apontar para um valor na memória do computador, no caso o número inteiro `10`, na linguagem de programação Java, e no Processing que nela é baseado, precisamos indicar qual o "tipo" do valor ou objeto armazenado, neste caso `int`, um número inteiro.  Um outro exemplo seria `float tamanho = 2.5;` em que o nome `tamanho` aponta para o valor `2.5` um número "de ponto flutuante", do tipo `float`.

Da mesma maneira precisamos indicar o tipo dos dados retornados por uma função (às vezes descrito como "o tipo da função"). Funções que não retornam nada são do tipo `void`, como `setup()`, `draw()`, `noStroke()` e `rect()`, por exemplo.

Os parâmetros ou argumentos que uma função recebe quando invocada, também tem tipos, que podem ser descobertos na documentação (no caso de funções pré-definidas ou de bibliotecas externas) ou na definição da função.

### Alguns tipos simples/primitivos

| tipo | descrição |
| --- | --- |
|`int`  |  número inteiro, como `-5`, `0` ou `42`
| `float`  | número com ponto flutante, como `6.267` (note que o separador decimal é o ponto)
| `boolean` |  armazena `true` ou `false`
| `char`| uma letra ou glifo UNICODE, como `'a'` (note as aspas simples)
| `color`  |  armazena uma cor, que pode ser construída com `color(R,G,B)` ou `color(R,G,B,Alfa)`
| `void`| o "vazio" é o tipo das funções que nada retornam

### Alguns tipos de objetos/classes 

| tipo/classe | descrição |
| --- | --- |
| `String`  | cadeia de caracteres, `“texto”` (note as aspas duplas)
| `PImage` | imagens raster/bitmap
| `PShape` | formas vetorais, como as descritas num SVG
| `PVector` | vetor, comunmente usado para descreve posição, velocidade ou aceleração em 2 ou 3 dimensões 
