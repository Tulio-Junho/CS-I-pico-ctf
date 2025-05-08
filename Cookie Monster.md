# Cookie Monster Secret Recipe
###### Solved by @Tulio-Junho
> This is a CTF about Source Code Inspection
## About the Challenge
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?
You can access the Cookie Monster "here" and good luck
## Solution
Para este desafio, devemos primeiro entrar no link, o qual pode ser encontrado clicando em [here](http://verbal-sleep.picoctf.net:56571/), e então, seremos redirecionados à uma página que deve ser colocado o login e senha.

[![Captura-de-tela-2025-05-02-131115.png](https://i.postimg.cc/t4MdJL8p/Captura-de-tela-2025-05-02-131115.png)](https://postimg.cc/fVYSggwr)

Após tentarmos um login e senha aleatório, obteremos essa página:

[![Captura-de-tela-2025-05-07-230411.png](https://i.postimg.cc/nzs88b75/Captura-de-tela-2025-05-07-230411.png)](https://postimg.cc/fthqXP8j)

O site nos dá uma dica, vista em "Hint: Have you checked your cookies lately?", de olharmos os cookies da página, os quais iremos chegar agora. Para isso, primeiro deve-se clicar com o botão direito do mouse
dentro da página e depois em inspecionar:

[![certa.png](https://i.postimg.cc/5tsH7vqg/certa.png)](https://postimg.cc/qtCMgNF6)

Após isso, devemos clicar em "aplicativos"

[![aplicativo.png](https://i.postimg.cc/JzkW0Bhn/aplicativo.png)](https://postimg.cc/9DCkN0Z5)

E depois em cookies, onde na primeira linha da planilha estará nossa flag criptografa:

[![cookie.png](https://i.postimg.cc/151dBYR9/cookie.png)](https://postimg.cc/6Tzz5cGS)

Nossa flag é esta: "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzk2RjU4REFCfQ%3D%3D", que é o mesmo que "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzk2RjU4REFCfQ==", pois "%3D%3D" é uma forma codificada de "==", os quais são uns dos principais símbolos para uma mensagem encriptada em base64. Descriptografando-a utilizando o site "base64decoder", recebemos a flag.

[![Captura-de-tela-2025-05-07-230234.png](https://i.postimg.cc/4yh9qdB0/Captura-de-tela-2025-05-07-230234.png)](https://postimg.cc/kRqGtnrN)

>`picoCTF{c00k1e_m0nster_l0ves_c00kies_96F58DAB}`

