# Cookie Monster Secret Recipe
###### Solved by @Tulio-Junho
> This is a CTF about Source Code Inspection
## About the Challenge
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?
You can access the Cookie Monster "here" and good luck
## Solution
Para este desafio, devemos primeiro entrar no link, o qual pode ser encontrado clicando em "here" (  http://verbal-sleep.picoctf.net:56571/  ), e então, seremos redirecionados à uma página que deve ser colocado o login e senha.
Após errarmos de propósito uma vez, o acesso será negado, porém, se inspecionarmos a página e depois em "aplicativo" e clicarmos em "cookie", abrirá uma planilha na qual aparecerá a flag criptograda. "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzk2RjU4REFCfQ%3D%3D".
Logo, percebe-se que a flag em específico está criptograda em Base64. Descriptografando-a, temos a flag.
>`picoCTF{c00k1e_m0nster_l0ves_c00kies_96F58DAB}`

