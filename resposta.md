# Flag Hunters
###### Solved by @Tulio-Junho
> This is a CTF about [Reverse Engineering]
## About the Challenge
Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you.
The program's source code can be downloaded "here".
Connect to the program with netcat:
$ nc verbal-sleep.picoctf.net 59898
## Solution
para resolver este desafio, primeiro deve-se baixar o arquivo e abrí-lo, neste arquivo terá um código na linguagem Python, o qual iremos analisar. No primeiro contato com o código, percebe-se uma letra de música
com um verso aparente, o qual é retratado como "secret intro", a qual só pode ser ativada quando algo no código acontece (falarei do código ao recorrer).

[![imagem-1.png](https://i.postimg.cc/VNqCqgCx/imagem-1.png)](https://postimg.cc/B8vbsxNp)

Ao usar o kali linux, abrir o prompt de comando e digitar o comando previsto 'nc verbal-sleep.pictoctf.net 59898', começará a imprimir uma música, a qual poucos versos após aparece "Crowd:", indicando ao usuário
que deve-se digitar algo.
[![Captura-de-tela-2025-05-02-174607.png](https://i.postimg.cc/3wFsDyKK/Captura-de-tela-2025-05-02-174607.png)](https://postimg.cc/LqhCc8Y7)

A princípio, podemos digitar qualquer frase ou palavra que o código voltará a imprimir o restante da música (com o adicional que em todos os "Crowds" conseguintes aparecerá a frase ou palavra escrita.
Nesse momento, devemos olhar ao restante do código e entender o que está acontecendo e como podemos resolver a questão.

[![Captura-de-tela-2025-05-02-174856.png](https://i.postimg.cc/wvKnPh0c/Captura-de-tela-2025-05-02-174856.png)](https://postimg.cc/1gHWVNxf)

o código funciona a partir de uma lógica de leitura e execução sequencial de linhas de uma música. Ele percorre uma lista de instruções (song lines), tratando comandos especiais. Porém, ao invés de começar como 
qualquer outro código comum com o 0 em sua contagem de linhas, este em específico começa em 1, gerando a música inteira sem a "secret intro". Neste caso, poderíamos usar o RETURN 0 quando aparecesse o "crowd", entretanto,
como visto na linha 121 do código baixado, caso haja a leitura de RETURN (0 a 9), a contagem de linhas começará também em 1. Visto isso, podemos usar um "macete" simples em que escrevemos qualquer palavra ou frase quando
aparecer o próximo crowd e logo em seguida um ponto e vírgula " ; ", isso gera uma quebra de leitura caso haja algo a mais escrito. Então, podemos justamente colocar o RETURN 0 após esse ponto e vírgula, pois o código entenderá 
que é um comando para zerar a contagem de linhas, chegando assim, na intro secreta da música, entregando a nós a flag.
[![Captura-de-tela-2025-05-02-180126.png](https://i.postimg.cc/BQ2mmXzH/Captura-de-tela-2025-05-02-180126.png)](https://postimg.cc/Ln6kX628)

>`picoCTF{70637h3r_f0r3v3r_c659e814}`
