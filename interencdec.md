# Interencdec
###### Solved by @Tulio-Junho
> This is a CTF about [decryption]
## About the Challenge
Can you get the real meaning from this file.
Download the file "here".
## Solution
À princípio, para resolver este desafio, deve-se primeiro baixar o arquivo, o qual encontra-se clicando em "here" na descrição. Após isso, abra-o em um bloco de notas e lá estará uma mensagem encriptada.

[![Captura-de-tela-2025-05-07-160522.png](https://i.postimg.cc/GpxQbNhL/Captura-de-tela-2025-05-07-160522.png)](https://postimg.cc/B8tDgmKk)

Pode-se entender que a mensagem está encriptada em base64, pois há dois sinais de "=" em seu final. Utilizando o site "Base64decode" pude copiar a mensagem vista e descriptografá-la. 

[![Captura-de-tela-2025-05-07-160746.png](https://i.postimg.cc/DzGrxwMY/Captura-de-tela-2025-05-07-160746.png)](https://postimg.cc/bGzSJp8Q)

Após a descriptografia, temos a seguinte flag ainda encriptada "  b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='  ", a qual ainda se encontra em base64, porém, há neste caso em volta da flag a letra b
e duas aspas, as quais deve-se tirar para que assim haja outra criptografia com base em base64. Dessa forma, tirando os caracteres os quais estão nos atrapalhando, chegamos nisto " d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ== ",
o qual novamente devemos usar o site "base64decoder" para descriptografá-lo.

[![Captura-de-tela-2025-05-07-161218.png](https://i.postimg.cc/wTXx68sR/Captura-de-tela-2025-05-07-161218.png)](https://postimg.cc/JGhCqFxR)

Agora, com a flag que antes estava em base64 descriptografada, vê-se que a mesma ainda está encriptograda, mas agora com uma das criptografias mais antigas existentes, a cifra de césar. " wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6} ".
Utilizando o site "dcode", pude descriptografar esta cifra de césar, nos dando a flag desejada.

[![Captura-de-tela-2025-05-07-161707.png](https://i.postimg.cc/bYWJL91L/Captura-de-tela-2025-05-07-161707.png)](https://postimg.cc/4nvsxtLh)

>	picoCTF{caesar_d3cr9pt3d_b204adc6}
