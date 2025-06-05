# You either know, XOR you don't
###### Solved by @Tulio-Junho
> This is a CTF about XOR
## About the Challenge
[![abc.png](https://i.postimg.cc/Hnq7d3yj/abc.png)](https://postimg.cc/jnhjhHvr)

I've encrypted the flag with my secret key, you'll never be able to guess it.
"0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104"

Hint:Remember the flag format and how it might help you in this challenge!

## Solution
Para resolver este desafio, devemos primeiro escrever o seguinte código em [Python](https://www.python.org/) e irei analisá-lo comando por comando:

Esté é o código:
[![aa.png](https://i.postimg.cc/2jxBqxjW/aa.png)](https://postimg.cc/PNPq9Ywf)

Discutirei os comandos a seguir:

[![aaa.png](https://i.postimg.cc/zGwcRMMN/aaa.png)](https://postimg.cc/JsnqfTMY)

Primeiro o código define uma função [XOR](https://pt.wikipedia.org/wiki/Ou_exclusivo) que recebe dois [arrays de bytes](https://www.geeksforgeeks.org/python-bytearray-function/) 
e retorna um novo array de bytes resultante da operação XOR entre cada par de bytes das duas entradas. 
O XOR é uma operação comum em [criptografia](https://pt.wikipedia.org/wiki/Criptografia), que compara os bits de dois números e retorna 1 quando eles são diferentes, e 0 quando são iguais.
No Python, o operador " ^ " faz essa operação bit a bit.

[![aaaa.png](https://i.postimg.cc/W4k6kJtk/aaaa.png)](https://postimg.cc/HJTyGnwY)

Em seguida, o código define uma variável "encrypted_bytes", que é uma sequência de bytes gerada a partir de uma string hexadecimal. 
Essa string representa dados criptografados da flag criptografada. 

Depois disso, há uma variável "key_bytes" com o valor " b"crypto{" ", que é parte da flag usada para tentar descriptografar a mensagem. 
A parte da flag está no formato de bytes, e como ela tem apenas sete caracteres, a operação de XOR será feita apenas nos primeiros sete bytes da mensagem criptografada. 
Isso acontece porque a [função zip](https://www.w3schools.com/python/ref_func_zip.asp) usada na função xor para no menor dos dois comprimentos, ou seja, só junta o que tiver correspondência nos dois arrays.

[![a.png](https://i.postimg.cc/SRhrqLLr/a.png)](https://postimg.cc/xJ6H3z4J)

A última linha do código aplica a função xor entre os bytes criptografados e a parte da flag ' b"crypto{" ', e tenta decodificar o resultado como uma string. 
A expectativa é que isso revele os primeiros caracteres da mensagem original, e como a parte da flag já começa com "crypto{", o objetivo é descobrir o restante da chave para decifrar a mensagem inteira.

Executando este código, temos a saída "myXORke+y_QHOMe$~seG8bGURNDFWg)a|TM!an", da qual usaremos apenas o "myXorke+y" pois do _ para frente não há uma frase com pelo menos um pouco sentido (Além de conter caracteres
não imprimíveis):
[![a.png](https://i.postimg.cc/TP9Z5w1f/a.png)](https://postimg.cc/2q1HPCnK)

Seguindo as [propriedades do comando XOR](https://pt.wikipedia.org/wiki/Ou_exclusivo), lembramos que o XOR é associativo, ou seja, "(a ⊕ b) ⊕ c" é igual a "a ⊕ (b ⊕ c)".
Portanto, aplicaremos essa propriedade agora, mudando o valor de "key_bytes" de "crypto{" para "myXORkey".
Dessa forma, encontraremos nossa flag:

[![aa.png](https://i.postimg.cc/yxyJwtTV/aa.png)](https://postimg.cc/p5yXj077)

>`crypto{1f_y0u_Kn0w_En0uGH_y0u_Kn0w_1t_4ll}`





