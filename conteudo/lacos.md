# Iteração / laços de repetição (loops)

## Sintaxe

O `for` permite controlar uma seqüência de repetições. A estrutura tem quatro partes:
*início, condição, coda* e *bloco a ser executado*.
As três primeiras partes, entre parênteses, são separadas por ponto e vírgula (`;`).
O laço continua, executando a parte final entre chaves (`{ }`), até que o teste seja avaliado como falso.

```java   
for (início [inicializa contador]; condição [testa contador]; coda [atualiza contador]) {
  Bloco de código a ser executado;
}
```

Quando a estrutura `for(){}` é executada, a seguinte sequência passos ocorre: 
1. os comandos em **início** são executados [em geral a inicialização de uma variável contador];
2. a **condição** ou expressão teste [normalmente comparando o contador para limitar o número de "voltas"] é avaliada verdadeira ou falsa (`true` ou `false`);
3. Caso a **condição** seja verdadeira (`true`), passa-se ao passo 4. Caso seja falsa (`false`), passa-se ao passo 6;
4. Executam-se os comandos contidos no **bloco de código** da estrutura em laço; 
5. Executam-se os comandos em **coda** [normalmente mudando o valor da variável contador] e passa-se ao passo 2;
6. Terminou o laço.

## Exemplos

### contator 
```pde
for (int i = 40; i < 80; i = i + 5) { 
  line(30, i, 80, i); 
}
```

### laços "aninhados" par fazer uma grade

```pde
for (int i = 30; i < 80; i = i + 10) { 
  for (int j = 0; j < 80; j = j + 10) { 
    ellipse(i, j, 5, 5); 
  } 
}
```
