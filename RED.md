# RED
###### Solved by Tulio-Junho
> This CTF is about [forensis]
## About the Challenge 
RED, RED, RED, RED
Download the image: "red.png"
## Solution
Para resolvermos este desafio, devemos baixar a imagem em [.png](https://pt.wikipedia.org/wiki/PNG) que a [página do desafio](https://play.picoctf.org/practice/challenge/460) nos dá, abrindo-a vê-se uma imagem de um simples quadrado vermelho.

[![Captura-de-tela-2025-05-07-162709.png](https://i.postimg.cc/Y2WM3GMw/Captura-de-tela-2025-05-07-162709.png)](https://postimg.cc/c60p1JvD)

No momento, pode-se pensar que não há o que fazer, porém, podemos usar o site [Aperi'Solve](https://www.aperisolve.com/),o qual é uma plataforma online que realiza análise de camadas em imagens desejadas. Dessa maneira, dando "upload" da imagem ao site percebe-se algo que antes não era visto.

[![Captura-de-tela-2025-05-07-163014.png](https://i.postimg.cc/4xmZC3jJ/Captura-de-tela-2025-05-07-163014.png)](https://postimg.cc/VJQ2nzYT)

Nessa parte onde se encontra o [Zsteg](https://commandmasters.com/commands/zsteg-common/) há criptografias com base em [base64](https://pt.wikipedia.org/wiki/Base64), utilizando o site [base64decode](https://www.base64decode.org/) para descriptografá-las, além de algumas criptografias que não são de nosso desejo, encontra-se nossa flag.

[![Captura-de-tela-2025-05-07-163254.png](https://i.postimg.cc/BQx8km9S/Captura-de-tela-2025-05-07-163254.png)](https://postimg.cc/yk8YSX8t)

> picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
