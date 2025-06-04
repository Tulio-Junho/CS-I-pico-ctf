# XOR Properties
###### Solved by @Tulio-Junho
> This is a CTF about XOR
## About the Challenge
[![Captura-de-tela-2025-06-04-172933.png](https://i.postimg.cc/pTXbfNF8/Captura-de-tela-2025-06-04-172933.png)](https://postimg.cc/Mc4FwFtK)

## Introdução
Para resolvermos este desafio devemos trabalhar com as propriedades matemáticas de [XOR](https://informedenoticias.com.br/glossario/o-que-e-xor-exclusive-or/), que como visto no desafio, a ferramenta XOR é
comutativa, associativa, tem identidade e se fizer um código sobre ele mesmo dá 0. Com isso, podemos fazer este desafio de maneira rápida se usarmos as propriedades de maneira correta.

## Solução

Usando as propriedades do XOR, escrevi um simples código em [python](https://pt.wikipedia.org/wiki/Python), o qual transforma cada chave em código binário e depois utiliza as seguintes propriedades as quais 
fazem com que as chaves sejam descobertas, após isso a flag será vista em código binario, utilizando a penultima linha do código para descriptografá-la e após isso o comando "print", teremos a flag! 

[![rnjoenjoneoniornir.png](https://i.postimg.cc/pLG9FsHy/rnjoenjoneoniornir.png)](https://postimg.cc/nXmc8YMt)

>`crypto{x0r_i5_ass0c1at1v3}`



