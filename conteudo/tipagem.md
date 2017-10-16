
# Variáveis, parâmetros e seus tipos

## Variáveis

Quando declaramos uma variável, por exemplo `int i = 10;`, o `i` aqui é um nome que vai apontar para um valor na memória do computador, no caso o número inteiro `10`, na linguagem de programação Java, e no Processing que nela é baseado, precisamos indicar qual o "tipo" do valor ou objeto armazenado, neste caso o tipo é `int`, um número inteiro.  

Um outro exemplo seria `float tamanho = 2.5;` em que o nome `tamanho` aponta para o valor `2.5`, um número "de ponto flutuante" (do tipo `float`). Ou ainda `String dev = "Luiza";`, em que `dev` aponta para o texto `Luiza` (um `String`).

## Conversão

É necessário por vezes converter os dados de um tipo para outro, como por exemplo o número sorteado por uma função `random()` que é um `float` pode ser convertido em `int`, sendo truncado (encurtado) se tiver uma parte não inteira. E números podem ser convertidos em texto (`String`).

```pde
int R = int(random(256));
println("Red: "+str(R));```

## Parâmetros e funções

Os parâmetros ou argumentos que uma função recebe quando invocada tem tipos, que podem ser descobertos na documentação (no caso de funções pré-definidas ou de bibliotecas externas) ou na definição da função. Da mesma forma os dados retornados pela função tem um tipo (às vezes descrito como "o tipo da função"). Funções que não retornam nada são do tipo `void`, como `setup()`, `draw()`, `noStroke()` e `rect()`, por exemplo.

A função `color()` do Processing, por exemplo, recebe como argumentos números inteiros e retorna uma cor:

`color minhaCor = color(255, 0, 0);  // A variável minhaCor aponta para uma cor vermelha na memória`

Podemos construir uma função que retorna uma cor também:

```pde
color corSorteada(int alpha) {
   int R = int(random(256);
   int G = int(random(256);
   int B = int(random(256);
   return color(R, G, B, alpha);
}
```

### Alguns tipos simples/primitivos

| tipo | descrição |
| --- | --- |
|`int`  |  número inteiro, como `-5`, `0` ou `42`
| `float`  | número com ponto flutante, como `.5` `3.` ou `6.267` (note que o separador decimal é o ponto)
| `boolean` |  valores `true` ou `false`
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
