# XOR Starter
###### Solved by @Tulio-Junho
> This is a CTF about XOR
## About the Challenge

[![Captura-de-tela-2025-06-04-163347.png](https://i.postimg.cc/zBkfF0h9/Captura-de-tela-2025-06-04-163347.png)](https://postimg.cc/JDGm13Pq)

Given the string label, XOR each character with the integer 13. Convert these integers back to a string and submit the flag as crypto{new_string}.

## Introdução

Este desafio consiste em traduzir a palavra "label" com o número "13" com a ferramenta [XOR](https://informedenoticias.com.br/glossario/o-que-e-xor-exclusive-or/), que consiste em transformar dois números
binários em um próximo, retornando "1" caso dois números de mesma ordem sejam diferentes e "0" caso sejam iguais. A imagem a seguir exemplifica isso:

[![Captura-de-tela-2025-06-04-163934.png](https://i.postimg.cc/NMC2qQGg/Captura-de-tela-2025-06-04-163934.png)](https://postimg.cc/vg9Z5F6j)

## Solution 

Para resolver este desafio, devemos primeiro traduzir a palavra "label" e o número "13" para [binário](https://www.todamateria.com.br/numeros-binarios/). Há várias de codificá-los, nesse desafio usarei a 
[tabela ASCII](https://www.ascii-code.com/pt) para visualização, o site [rapidtables](https://www.rapidtables.org/pt/convert/number/decimal-to-binary.html) para tradução de números decimais para binário e 
o site [convertbinary](https://pt.convertbinary.com/texto-para-binario/) para tradução de texto para binário. Visto as ferramentas, podemos começar a trabalhar.


### Texto "label" para binário

Usando o site antes visto [convertbinary](https://pt.convertbinary.com/texto-para-binario/) podemos digitar a palavra que queremos e ele nos dará o código binário dela, visto na imagem a seguir:

[![Captura-de-tela-2025-06-04-165444.png](https://i.postimg.cc/tTCp6FXC/Captura-de-tela-2025-06-04-165444.png)](https://postimg.cc/2qJsRbbP)

Logo, temos o código > 01101100 01100001 01100010 01100101 01101100 <, que usaremos em breve.

### Decimal 13 para binário 

Usando o site também antes visto [rapidtables](https://www.rapidtables.org/pt/convert/number/decimal-to-binary.html) podemos escrever o número que desejamos e retornará o código bínario dele:

[![Captura-de-tela-2025-06-04-165913.png](https://i.postimg.cc/FzykD2fV/Captura-de-tela-2025-06-04-165913.png)](https://postimg.cc/GTpppgx4)

Então, temos o código > 1101 <.
Agora que temos os dois códigos desejados começaremos a realmente usar a ferramenta XOR de comparação.

### Utilizando XOR

Organizando os códigos em um bloco de notas podemos comparar cada letra de "label", que agora são 5 códigos binários, com o código bínario do decimal 13 de várias formas, utilizarei o bloco de notas para maior 
sistematização do desafio. Começaremos com a letra "l":

[![Captura-de-tela-2025-06-04-170624.png](https://i.postimg.cc/KcwL7hzL/Captura-de-tela-2025-06-04-170624.png)](https://postimg.cc/K47RFVtv)

Utilizando a [tabela ASCII](https://www.ascii-code.com/pt) para visualização, temos que o código "01100001" é a letra "a". Guardada essa informação, iremos agora traduzir a letra "a" de "label", a qual, pela 
lógica inversa nos dará a letra "l":

[![Captura-de-tela-2025-06-04-171207.png](https://i.postimg.cc/LXFV2qYH/Captura-de-tela-2025-06-04-171207.png)](https://postimg.cc/Z9jNL5xg)

Agora a letra "b":

[![Captura-de-tela-2025-06-04-171330.png](https://i.postimg.cc/hj3Thfhz/Captura-de-tela-2025-06-04-171330.png)](https://postimg.cc/62nym6rt)

Em mesma lógica de visualização na tabela, agora é vista a letra "o" na descriptografia. Agora, a letra "e" de "label":

[![Captura-de-tela-2025-06-04-171526.png](https://i.postimg.cc/3xmRz9Gb/Captura-de-tela-2025-06-04-171526.png)](https://postimg.cc/cv10nRXQ)

A qual resulta em "h". Agora novamente o "l" que resulta na letra "a". Juntando as letras que achamos, temos a palavra "aloha", que é nossa flag.

>`crypto{aloha}`


