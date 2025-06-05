# Favourite Byte
###### Solved by Tulio-Junho
> This is a CTF about brute force
## About the Challenge

[![Captura-de-tela-2025-06-04-191304.png](https://i.postimg.cc/13LGWbsn/Captura-de-tela-2025-06-04-191304.png)](https://postimg.cc/tsNnJS1p)

For the next few challenges, you'll use what you've just learned to solve some more XOR puzzles.
I've hidden some data using XOR with a single byte, but that byte is a secret. Don't forget to decode from hex first.

## Introdution
Para realizar este desafio, devemos primeiro entender o que [brute force](https://www.kaspersky.com.br/resource-center/definitions/brute-force-attack), uma ferramenta que utiliza o método de tentativa e erro 
para conseguir informações.

## Solution
Para resolver esse desafio, devemos primeiro utilizar um código em [Python](https://pt.wikipedia.org/wiki/Python):

[![codigo.png](https://i.postimg.cc/90bYFjz8/codigo.png)](https://postimg.cc/H8JyBRwX)

Irei explicar cada um dos comandos para maior entendimento do código:

[![def.png](https://i.postimg.cc/FK2YcC29/def.png)](https://postimg.cc/t1NRGkqf)

* Este comando define a função XOR, que recebe o argumento "a" e "b", ambos em [código binário](https://www.todamateria.com.br/numeros-binarios/), sem ele não conseguimos começar o exercício pois necessitamos do comando
  XOR.

* para cada par (x,y), aplica-se a operação XOR bit a bit (x ^ y)

* zip(a,b) juntao so dois bytes par a par.

Após isso, é criada a variável "hex_string" que é a nossa string que guarda uma mensagem em hexadecimal.

[![Captura-de-tela-2025-06-04-211614.png](https://i.postimg.cc/4yNWpfLp/Captura-de-tela-2025-06-04-211614.png)](https://postimg.cc/HcR0ggCL)

Esse comando converte a string hexadecimal em bytes reais e os armazena em data.

[![bruteforce.png](https://i.postimg.cc/T2C7fb10/bruteforce.png)](https://postimg.cc/G9TJjHkT)

Agora, entenderemos como funciona esse brute force, que inicia um [loop](https://pt.wikipedia.org/wiki/Loop_(programa%C3%A7%C3%A3o)) que vai de 0 a 255 bytes, 
cobrindo todas as chaves possíveis de 1 byte. Em cada interação o valor "key" assume um valor diferente.

Depois, cria um [array](https://www.w3schools.com/python/python_arrays.asp) repetindo o valor de "key" para que fique do mesmo tamanho de data. Isso é necessário para fazer o XOR corretamente byte por byte.

Logo após, chama a função "xor" passando data e a sequência "key_bytes" como [argumento](https://www.pythonprogressivo.net/2018/07/Argumento-Parametros-Funcao-Python-tutorial.html#google_vignette),
o resultado é uma nova sequência de bytes após a ope´ração XOR entra cada byte da mensagem e da chave.

Mais tarde, em "try", o código tenta decodificar os bytes resultantes como texto [ASCII](https://www.ascii-code.com/pt), se todos os bytes representarem caracteres válidos, a conversão funciona.

Seguidamente, em "if all", o código verifica e garante que a mensagem tenha apenas texto legível.

Diante disso, chegamos ao último comando que é o "print",  que se a verificação e garantia do código ser legível for verdadeira, ele imprime o valor da chave e a mensagem decodificada. Pode ocorrer de acontecer
mais de uma impressão, porém, como no site do cryptohack sempre diz qual é o começo da flag -> "Enter flag here: crypto{FLAG}", distingui-se bem rápido qual é a verdadeira. Assim, termina-se o desafio.

>`crypto{0x10_15_my_f4v0ur173_by7e}`
