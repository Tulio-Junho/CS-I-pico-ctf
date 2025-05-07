# RED
###### Solved by Tulio-Junho
> This CTF is about [forensis]
## About the Challenge 
RED, RED, RED, RED
Download the image: "red.png"
## Solution
Para resolvermos este desafio, devemos baixar a imagem em png que o site nos dá, abrindo-a damos de cara com um simples quadrado vermelho.

[![Captura-de-tela-2025-05-07-162709.png](https://i.postimg.cc/Y2WM3GMw/Captura-de-tela-2025-05-07-162709.png)](https://postimg.cc/c60p1JvD)

No momento, pode-se pensar que não há o que fazer, porém, podemos usar um site " Aperi'Solve ", o qual detecta dados ocultos em imagens. Dessa maneira, usando o site, percebe-se algo que antes não era visto.

[![Captura-de-tela-2025-05-07-163014.png](https://i.postimg.cc/4xmZC3jJ/Captura-de-tela-2025-05-07-163014.png)](https://postimg.cc/VJQ2nzYT)

Nessa parte onde se encontra o "Zsteg" há criptografias com base em base64, utilizando o site "base64decode" para descriptografá-las, além de algumas frases sem sentido, encontra-se nossa flag.

[![Captura-de-tela-2025-05-07-163254.png](https://i.postimg.cc/BQx8km9S/Captura-de-tela-2025-05-07-163254.png)](https://postimg.cc/yk8YSX8t)

> picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
