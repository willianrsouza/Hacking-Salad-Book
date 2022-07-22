# Hacking-Salad-Book
My own hacking book, learning.  Boost your Pentest with these recipes.


## Protocolo Diffie-Hellman

   **Data Publicação:** 1976
   **Desenvolvido:** Whitefield e Martin
    
 - **Objetivo**
Resolver o problema de envio de uma chave secreta, por meio de comunicações inseguras. Utilizado exclusivamente para realizar trocas de chaves.

 - **Cálculo Simples Modular**

![enter image description here](https://skerritt.blog/media/diffie/9.png)

O calculo modular para a criptografia é interessante pois, realizar sua reversão, e encontrar o valor de input dos dados é extremamente incerto. É basicamente uma função de mão única.

**Prática**

 - **Step 1**

**Os usuários, definem um numero inteiro, exemplo: 5, e numero primo, exemplo: 17, e  o compartilham.**

***(Nota: Até o momento o Man in the Middle, consegue facilmente capturar essa escolha.)***

 - **Step 2**

Após essa definição, cada usuário escolhera individualmente um numero secreto. Esses números não serão transmitidos pela internet.

**Pedro**, escolhe: **24** 
**Willian**, escolhe: **52**

 - **Step 3**

Valores acordados, pelos usuários: **Inteiro: 5** , **Primo: 17**

**Pedro:**

**5^24 mod 17 = 16**

Pedro, envia o resultado para Willian. **Resultado: 16.**

***(Nota: Até o momento o Man in the Middle, consegue facilmente capturar essa escolha.)***

 - **Step 4**
 
*(Valor recebido de Pedro, é armazenado: **16.**)*
Agora já recebido o **resultado** de **Pedro**, **Willian** realizara a sua simples formula matemática.

Valores acordados, pelos usuários: **Inteiro: 5** , **Primo: 17**

**Willian:**  5^52 mod 17 = 13

Willian, envia o resultado para Pedro, esse valor é armazenado por Pedro. **Resultado: 13.**

***(Nota: Até o momento o Man in the Middle, consegue facilmente capturar essa escolha.)***

 - **Step 5**


Após cada usuário, possuírem os resultados de cada um. Cada um, irá fazer outro calculo modular:

**Willian:** 16^52 mod 17 = 1

**Pedro:** 13^24 mod 17 = 1

Os usuários utilizam os seus números secretos, que não foram transmitidos em momento algum, como expoente. Dessa forma os dois usuários, chegaram ao mesmo produto. Esse resultado, será a chave de criptografia.

 - **Conclusão:**

Os números secretamente escolhidos, não foram transmitidos pela internet, somente o produto gerado. Após a obtenção do produto de cada um, eles puderam realizar a formula para chegar ao um produto comum.
