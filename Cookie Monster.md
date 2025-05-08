# Cookie Monster Secret Recipe
###### Solved by @Tulio-Junho
> This is a CTF about Source Code Inspection
## About the Challenge
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?
You can access the Cookie Monster "here" and good luck
## Solution
Para este desafio, devemos primeiro entrar no link, o qual pode ser encontrado clicando em [here](http://verbal-sleep.picoctf.net:56571/), e então, seremos redirecionados à uma página que deve ser colocado o login e senha.

[![Captura-de-tela-2025-05-02-131115.png](https://i.postimg.cc/t4MdJL8p/Captura-de-tela-2025-05-02-131115.png)](https://postimg.cc/fVYSggwr)

Após tentarmos um login e senha aleatório, obteremos essa página, a qual nega o acesso ao usuário, porém nos mostra uma dica:

[![Captura-de-tela-2025-05-07-230411.png](https://i.postimg.cc/nzs88b75/Captura-de-tela-2025-05-07-230411.png)](https://postimg.cc/fthqXP8j)

O site nos dá uma dica, vista em "Hint: Have you checked your cookies lately?", de olharmos os cookies da página, os quais iremos chegar agora. Para isso, primeiro deve-se clicar com o botão direito do mouse
dentro da página e depois em inspecionar, para vermos o código [HTML](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Getting_started/Your_first_website/Creating_the_content) da página:

[![certa.png](https://i.postimg.cc/5tsH7vqg/certa.png)](https://postimg.cc/qtCMgNF6)

Após isso, devemos clicar em "aplicativos". Os navegadores modernos organizam os dados locais, como [cookies](https://www.kaspersky.com.br/resource-center/definitions/cookies) e outros, na aba "Aplicativos" das ferramentas de desenvolvedor. Essa organização facilita a visualização e manipulação desses dados, que são essenciais para o funcionamento de muitas aplicações web.

[![aplivativosadfasdfasdf.png](https://i.postimg.cc/x8mVF6sp/aplivativosadfasdfasdf.png)](https://postimg.cc/K3mW1Dht)


E depois em cookies, onde na primeira linha da planilha estará nossa flag criptografa:

[![cookie.png](https://i.postimg.cc/151dBYR9/cookie.png)](https://postimg.cc/6Tzz5cGS)

Agora que temos a planilha dos cookies da página, deve-se clicar com o botão direito sobre o valor deste único cookie e após isso clicar em "Edit Valor", para conseguir copiar a nossa flag.

[![Captura-de-tela-2025-05-08-195446.png](https://i.postimg.cc/SN0hzpsB/Captura-de-tela-2025-05-08-195446.png)](https://postimg.cc/Wt7KQC08)

Nossa flag é esta: "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzk2RjU4REFCfQ%3D%3D", que é o mesmo que "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzk2RjU4REFCfQ==", pois "%3D%3D" é uma forma codificada de "==", os quais são uns dos principais símbolos para uma mensagem encriptada em [base64](https://pt.wikipedia.org/wiki/Base64). Descriptografando-a utilizando o site [base64decoder](https://www.base64decode.org/), recebemos a flag.

[![Captura-de-tela-2025-05-07-230234.png](https://i.postimg.cc/4yh9qdB0/Captura-de-tela-2025-05-07-230234.png)](https://postimg.cc/kRqGtnrN)

>`picoCTF{c00k1e_m0nster_l0ves_c00kies_96F58DAB}`

