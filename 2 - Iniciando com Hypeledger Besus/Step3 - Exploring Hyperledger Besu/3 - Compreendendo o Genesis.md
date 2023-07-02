Genesis 

O primeiro bloco em uma blockchain é chamado de bloco de gênese. O bloco de gênese da rede principal Ethereum - bloco 0 - foi minerado em 30 de julho de 2015. Para ingressar ou criar qualquer rede, os dados do bloco de gênese devem ser incluídos. Portanto, o arquivo genesis define os dados que estão no primeiro bloco de uma blockchain, bem como regras para a própria blockchain. Se um novo nó ou validador tentar se juntar ao blockchain, ele usará o arquivo genesis como ponto de partida para recriar o histórico da cadeia para sincronizar com a rede existente.

O arquivo genesis para a rede principal Ethereum, junto com as redes de teste suportadas, está incluído no download do Besu. Ao criar uma rede privada, um arquivo genesis deve ser fornecido. O arquivo genesis é um arquivo formatado em JSON. Parece com o abaixo:

```
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

Neste exemplo específico, o arquivo genesis é para uma rede privada IBFT 2.0.

```
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

A seção de chave de configuração contém as seguintes informações sobre o blockchain: "chainId": 2018

- O ID da cadeia (ChainID) controla o processo de assinatura da transação, fornecendo um identificador exclusivo para permitir que o hash das transações assinadas funcione apenas na rede associada ao ID da cadeia (CHAINID) correspondente. A Proposta de Melhoria Ethereum 155 (EIP-155) fornece mais informações sobre a lógica por trás do ID da cadeia (CHAINID). A maioria dos IDs de cadeia (ChainID) corresponde ao ID de rede da rede. Nesse caso, 2018 refere-se ao ID da cadeia associado a uma cadeia de desenvolvimento. Para obter uma lista de IDs de rede e cadeia, consulte a documentação do Hyperledger Besu, [NetworkID-And-ChainI](https://besu.hyperledger.org/en/stable/Concepts/NetworkID-And-ChainID/)


"muirglacierblock": 0,
Este campo é chamado de “bloco de marco”. Muir Glacier refere-se a uma atualização de rede específica que ocorreu no bloco 9.200.000 na rede principal Ethereum. Para redes privadas, como a que está sendo criada neste exemplo, o nome do bloco de marco mais recente pode ser listado e definido como o bloco de gênese. Aqui você pode ver uma lista continuamente atualizada de atualizações de rede e os blocos associados para Ethereum.

"ibft2":
Isso especifica que o protocolo de consenso para o blockchain é IBFT 2.0. As opções disponíveis para especificar o mecanismo de consenso estão disponíveis na documentação do Hyperledger Besu, com uma visão geral dos protocolos de consenso de prova de autoridade (PoA) disponíveis aqui.

Dentro da especificação, os três campos a seguir são fornecidos:

"blockperiodseconds": 2,
O tempo mínimo de bloqueio, em segundos. Neste caso, após dois segundos, um novo bloco será proposto pela rede.

"comprimento da época": 30000,
O número de blocos nos quais redefinir todos os votos. Os votos referem-se à votação dos validadores para adicionar ou remover validadores da rede. Neste caso, após a criação de 30.000 blocos, esta rede IBFT 2.0 descartará todos os votos pendentes coletados dos blocos recebidos. As propostas existentes permanecem em vigor e os validadores adicionam novamente seu voto na próxima vez que criarem um bloco.

"requesttimeoutseconds": 4
O tempo em que um novo bloco deve ser proposto ou então um novo validador será atribuído pela rede. Se um validador cair, o tempo limite da solicitação garante que a proposta de um novo bloco passe para outro validador. Os segundos de tempo limite da solicitação devem ser definidos como o dobro do tempo mínimo de bloqueio (blockperiodseconds), por isso é 4.


A segunda seção, começando com "nonce": "0x0", contém informações sobre o bloco genesis:

```
{
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