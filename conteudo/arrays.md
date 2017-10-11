# Arrays

Arrays são variáveis ‘compostas’ com múltiplos elementos de um mesmo tipo. Precisam ser declarados, como variáveis normais, porém precisam também ser criados ou inicializados com o número de posições, isto é o número de itens que poderão referenciar na memória do computador. Para ler um item ou elemento usamos um índice entre colchetes (`[ ]`). O primeiro elemento é o de índice 0, como em `nome[0]`, por exemplo.

### Sintaxe

```java
tipo[] nome_do_array; // declarar com tipo uma variável array
nome_do_array = new tipo[número de itens]; // criar um array vazio
nome_do_array[índice] = valor;// atribuir um valor a um elemento
// declarar array com tipo, cria;e atribuir valores de uma vez
tipo[] nome_do_array = { valor_separados_por_vírgulas }; 
// para ler elementos, indicar o índice
println(nome_do_array[índice]);  // 0 é o índice do primeiro elemento
```

### Exemplos

```java
// um array de inteiros
int[] w = { 50, 61, 83, 69, 71, 50, 29, 31, 17, 39 };
// para ler o primeiro valor do Array
rect(10, 10, w[0], 8)
// para ler todos os valores um por vez!!!
// nome_do_array.length contém o número de elementos.
for (int i = 0; i < w.length; i++) {
  rect(0, i*10, w[i], 8);
}
// outra maneira! 
int i = 0;
for (int n : w) { // ao ‘n’ vai ser atribuído um valor por vez! 
  rect(0, i*10, w[n], 8);
  i++;
}

// Array de Strings
String frase = "Paca tatu cotia não"; // variável String comum
String[] lista = split(frase, " ");  // separando num array de Strings chamado ‘lista’
for (String palavra : lista) {      //  para cada ‘palavra’ da ‘lista’
  println(palavra);                // imprima a ‘palavra’ no console
}
```

Referência: https://processing.org/tutorials/arrays/
Outros assuntos relacionados:
Métodos de manipulação de arrays, arrays 2D e ArrayLists (listas dinâmicas).
