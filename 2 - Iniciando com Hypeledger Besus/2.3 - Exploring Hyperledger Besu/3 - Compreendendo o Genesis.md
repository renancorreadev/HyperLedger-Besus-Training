## Genesis

O primeiro bloco em uma blockchain é chamado de bloco de gênese. O bloco de gênese da rede principal Ethereum - bloco 0 - foi minerado em 30 de julho de 2015. Para ingressar ou criar qualquer rede, os dados do bloco de gênese devem ser incluídos. Portanto, o arquivo genesis define os dados que estão no primeiro bloco de uma blockchain, bem como regras para a própria blockchain. Se um novo nó ou validador tentar se juntar ao blockchain, ele usará o arquivo genesis como ponto de partida para recriar o histórico da cadeia para sincronizar com a rede existente.

O arquivo genesis para a rede principal Ethereum, junto com as redes de teste suportadas, está incluído no download do Besu. Ao criar uma rede privada, um arquivo genesis deve ser fornecido. O arquivo genesis é um arquivo formatado em JSON. Parece com o abaixo:

```json
{
  "config": {
    "chainId": 2018,
    "muirglacierblock": 0,
    "ibft2": {
      "blockperiodseconds": 2,
      "epochlength": 30000,
      "requesttimeoutseconds": 4
    }
  },
  "nonce": "0x0",
  "timestamp": "0x58ee40ba",
  "extraData": "0xf83ea00000000000000000000000000000000000000000000000000000000000000000d5949811ebc35d7b06b3fa8dc5809a1f9c52751e1deb808400000000c0",
  "gasLimit": "0x1fffffffffffff",
  "difficulty": "0x1",
  "mixHash": "0x63746963616c2062797a616e74696e65206661756c7420746f6c6572616e6365",
  "coinbase": "0x0000000000000000000000000000000000000000",
  "alloc": {
    "9811ebc35d7b06b3fa8dc5809a1f9c52751e1deb": {
      "balance": "0xad78ebc5ac6200000"
    }
  }
}
```

### Neste exemplo específico, o arquivo genesis é para uma rede privada IBFT 2.0.

```json
{
  "config": {
    "chainId": 2018,
   "muirglacierblock": 0,
    "ibft2": {
      "blockperiodseconds": 2,
      "epochlength": 30000,
      "requesttimeoutseconds": 4
    }
  }
}
```
### A seção de chave de configuração contém as seguintes informações sobre o blockchain:

- **"chainId": 2018**: O ID da cadeia (ChainID) controla o processo de assinatura da transação, fornecendo um identificador exclusivo para permitir que o hash das transações assinadas funcione apenas na rede associada ao ID da cadeia correspondente. A Proposta de Melhoria Ethereum 155 (EIP-155) fornece mais informações sobre a lógica por trás do ID da cadeia. A maioria dos IDs de cadeia corresponde ao ID de rede da rede. Nesse caso, 2018 é o ID da rede privada IBFT2.0.
- **"muirglacierblock": 0**: O bloco Muir Glacier é um hard fork da rede Ethereum Mainnet que ocorreu no bloco 9.200.000 para evitar o atraso do ajuste de dificuldade devido ao bug do relógio do Ethereum.
- **"ibft2"**: Essa seção define as configurações específicas do mecanismo de consenso IBFT 2.0.

Depois de definir a configuração, outras informações do bloco de gênese são fornecidas:

- **"nonce": "0x0"**: Um número aleatório usado na mineração para encontrar o valor adequado do hash.
- **"timestamp": "0x58ee40ba"**: O carimbo de data/hora em que o bloco foi minerado.
- **"extraData": "0xf83ea000...0000000000c0"**: Dados extras específicos para a rede ou blockchain.
- **"gasLimit": "0x1fffffffffffff"**: O limite máximo de gás que pode ser consumido em um bloco.
- **"difficulty": "0x1"**: A dificuldade do bloco.
- **"mixHash": "0x63746963616c2062797a616e74696e65206661756c7420746f6c6572616e6365"**: O hash da combinação de valores usados na mineração.
- **"coinbase": "0x0000000000000000000000000000000000000000"**: A conta que receberá a recompensa pela mineração do bloco.
- **"alloc"**: As alocações iniciais de saldo para contas específicas. Neste exemplo, a conta "9811ebc35d7b06b3fa8dc5809a1f9c52751e1deb" tem um saldo inicial de "0xad78ebc5ac6200000" (100.000 ETH).
