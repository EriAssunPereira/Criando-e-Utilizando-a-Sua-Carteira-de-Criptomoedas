# Criando-e-Utilizando-a-Sua-Carteira-de-Criptomoedas

Vamos dividir o projeto em módulos para facilitar o entendimento. Aqui está uma visão geral do que faremos:

1. **Gerador de Chaves Pública e Privada:**
   - Vamos criar um algoritmo para gerar um par de chaves: uma chave pública e uma chave privada.
   - A chave pública é usada para receber bitcoins, enquanto a chave privada é usada para assinar transações.
   - Exemplo prático: Usando bibliotecas como `bitcoinjs-lib` ou `pycryptodome`, podemos gerar essas chaves.

2. **Criação de Endereços Bitcoin:**
   - A partir da chave pública, podemos derivar um endereço Bitcoin.
   - O endereço é uma representação legível por humanos da chave pública.
   - Exemplo prático: Usando a chave pública gerada anteriormente, podemos obter o endereço correspondente.

3. **Importação no Electrum:**
   - O Electrum é uma carteira de desktop popular para Bitcoin.
   - Vamos importar nossa chave privada no Electrum para acessar nossa carteira.
   - Exemplo prático: Abrir o Electrum, selecionar "Importar chave privada" e inserir nossa chave privada.

4. **Envio de Criptomoedas:**
   - Agora que temos nossa carteira no Electrum, podemos enviar e receber bitcoins.
   - Exemplo prático: Enviar uma pequena quantidade de bitcoins para outro endereço usando o Electrum.

Lembre-se de que a segurança é fundamental ao lidar com chaves privadas. Mantenha sua chave privada em local seguro e não a compartilhe com ninguém.

Vamos criar um exemplo prático de geração de chaves e endereços Bitcoin:

1. **Gerando um Par de Chaves:**
   - Usaremos a biblioteca `bitcoinjs-lib` para gerar um par de chaves pública e privada.
   - Primeiro, instalaremos a biblioteca (se ainda não estiver instalada):
     ```
     npm install bitcoinjs-lib
     ```
   - Agora, no código JavaScript:
     ```javascript
     const bitcoin = require('bitcoinjs-lib');

     // Gerar um novo par de chaves
     const keyPair = bitcoin.ECPair.makeRandom();

     // Exibir a chave privada e pública
     console.log('Chave Privada (WIF):', keyPair.toWIF());
     console.log('Chave Pública:', keyPair.publicKey.toString('hex'));
     ```

2. **Derivando um Endereço Bitcoin:**
   - A partir da chave pública, podemos obter o endereço Bitcoin.
   - Vamos usar a rede de teste (testnet) para fins de exemplo:
     ```javascript
     const { address } = bitcoin.payments.p2pkh({ pubkey: keyPair.publicKey, network: bitcoin.networks.testnet });
     console.log('Endereço Bitcoin:', address);
     ```

3. **Importando no Electrum:**
   - Abra o Electrum e vá para "Arquivo" > "Nova/Restaurar".
   - Selecione "Importar chaves privadas" e insira a chave privada gerada.
   - Agora você pode acessar sua carteira no Electrum.

4. **Enviando Criptomoedas:**
   - Com sua carteira no Electrum, envie uma pequena quantidade de bitcoins para outro endereço.

Lembre-se de que este é apenas um exemplo educacional. Na prática, use carteiras seguras e mantenha suas chaves privadas protegidas.
