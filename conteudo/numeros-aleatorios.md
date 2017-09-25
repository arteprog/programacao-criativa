### Números (pseudo)aleatórios

Cada vez que chamamos a função `random()` com um parâmetro, como em `float sorteio = random(1);` um número entre zero e o parâmetro passado, o limite superior, é "sorteado" (não incluido este limite superior no sorteio).

Se dois parâmetros forem usados, por exemplo `random (-5, 5);` serão sorteados números entre -5 (incluso) e 5 (não incluso).

Podemos obter números inteiros convertendo o valor usando `int()`, como em `int sorteio_inteiro = int(random(2))`.

