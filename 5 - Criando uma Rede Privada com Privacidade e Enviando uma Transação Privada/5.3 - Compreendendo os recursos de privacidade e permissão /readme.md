# Privacidade e Permissões

[Privacidade](https://besu.hyperledger.org/en/stable/Concepts/Privacy/Privacy-Overview/), no contexto do Hyperledger Besu, refere-se à capacidade de manter transações entre dois ou mais participantes ocultas de outros participantes da rede. Isso é feito usando:

- [Transações Privadas](https://besu.hyperledger.org/en/stable/Concepts/Privacy/Private-Transactions/)
  Transações enviadas na rede blockchain que especificam os endereços e/ou nós que recebem a transação e podem ver o conteúdo. As transações privadas são criadas e enviadas usando métodos de API diferentes das transações que não são privadas. As diferenças entre os métodos de API para transações privadas são compartilhadas com mais detalhes na documentação do Hyperledger Besu,  ["Crating and Sending Private Transactions"](https://besu.hyperledger.org/en/stable/HowTo/Send-Transactions/Creating-Sending-Private-Transactions/).

- [Grupos de privacidade](https://besu.hyperledger.org/en/stable/Concepts/Privacy/Privacy-Groups/)
  Nós que compartilham um estado privado que não é compartilhado com o blockchain geral (o estado compartilhado por todos os nós dentro do blockchain, incluindo os nós de privacidade é chamado de estado mundial ou estado global). Os grupos de privacidade podem ser [flexíveis](https://besu.hyperledger.org/stable/private-networks/concepts/privacy/privacy-groups), o que significa que nós podem ser adicionados ou removidos do grupo de privacidade. Os grupos de privacidade flexíveis usam um contrato inteligente para permitir a adição ou exclusão de nós do grupo de privacidade. Os grupos de privacidade podem ser configurados em um único nó, o que é conhecido como multilocação [(multi-tenancy) ](https://besu.hyperledger.org/stable/private-networks/concepts/privacy/multi-tenancy) (vários locatários no mesmo nó). Como os inquilinos estão no mesmo nó, um JSON Web Token (JWT) é necessário para autenticar cada inquilino ao usar a API JSON-RPC para enviar transações.

  O Hyperledger Besu oferece opções para transações privadas e grupos de privacidade. As opções são detalhadas abaixo e cada uma contém um tutorial de exemplo:

### Tutoriais Hyperledger Besus

  - [Início rápido de desenvolvimento](https://besu.hyperledger.org/stable/private-networks/tutorials/quickstart)
  - [Crie uma rede privada usando QBFT](https://besu.hyperledger.org/stable/private-networks/tutorials/qbft)
  - [Crie uma rede privada usando IBFT 2.0](https://besu.hyperledger.org/stable/private-networks/tutorials/ibft)
  - [Crie uma rede privada usando o Clique](https://besu.hyperledger.org/stable/private-networks/tutorials/clique)
  - [Crie uma rede privada usando Ethash](https://besu.hyperledger.org/stable/private-networks/tutorials/ethash)

#### Redes Privadas
- [Crie uma rede habilitada para privacidade usando o Quorum Developer Quickstart](https://besu.hyperledger.org/stable/private-networks/tutorials/privacy/quickstart)
  
- [Crie uma rede habilitada para privacidade (Create a privacy-enabled network)](https://besu.hyperledger.org/stable/private-networks/tutorials/privacy)

- [Configurar um nó multilocatário (Configure a multi-tenant node)](https://besu.hyperledger.org/stable/private-networks/tutorials/privacy/multi-tenancy)

- [Use o exemplo de vários nós na biblioteca cliente web3js-quorum](https://besu.hyperledger.org/stable/private-networks/tutorials/privacy/web3js-quorum)

#### Rede autorizada (permissioned network)

- [Crie uma rede autorizada](https://besu.hyperledger.org/stable/private-networks/tutorials/permissioning)
- [Comece com permissão onchain](https://besu.hyperledger.org/stable/private-networks/tutorials/permissioning/onchain)
- [Atualizar contratos de permissão (upgrade-contracts)](https://besu.hyperledger.org/stable/private-networks/tutorials/permissioning/upgrade-contracts)


#### Deploys de Smart Contracts 
- [Implante contratos inteligentes em Ethereum](https://besu.hyperledger.org/stable/private-networks/tutorials/contracts)
- [Transferir fundos entre contas em uma transação](https://besu.hyperledger.org/stable/private-networks/tutorials/contracts/transfer-funds)
- [Interaja com contratos inteligentes implantados](https://besu.hyperledger.org/stable/private-networks/tutorials/contracts/interact)

#### Implantar exemplo de rede privada com Kubernetes 

- [Implantar em um ambiente local](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/playground)
- [Criar um cluster](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/cluster)
- [Implantar gráficos](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/charts)
- [Use o Explorador de Quórum](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/quorum-explorer)
- [Manutenção com Kubernetes](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/maintenance)
- [Implantar para produção](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/production)
- [Configurar o modo Kubernetes no Gerenciador NAT](https://besu.hyperledger.org/stable/private-networks/tutorials/kubernetes/nat-manager)

#### Implantar exemplo de rede privada no Azure
[Deploy de uma rede privada IBFT 2.0 network no Azure](https://besu.hyperledger.org/stable/private-networks/tutorials/azure)


[Contas para Testes](https://besu.hyperledger.org/stable/private-networks/reference/accounts-for-testing)


### Sobre permissões

A [permissão local](https://besu.hyperledger.org/stable/private-networks/how-to/use-permissioning/local) é feita no nível do nó. 
Cada nó na rede pode usar um arquivo de configuração de permissão para especificar as contas e os nós que podem participar da rede. 
Isso é feito usando um arquivo .toml que é colocado no diretório de dados de cada nó (como visto nos exemplos anteriores). 

Abaixo está um exemplo de um arquivo de configuração de permissão:

```js
accounts-allowlist=["0xb9b81ee349c3807e46bc71aa2632203c5b462032", "0xb9b81ee349c3807e46bc71aa2632203c5b462034"]

nodes-allowlist=[
  "enode://7e4ef30e9ec683f26ad76ffca5b5148fa7a6575f4cfad4eb0f52f9c3d8335f4a9b6f9e66fcc73ef95ed7a2a52784d4f372e7750ac8ae0b544309a5b391a23dd7@127.0.0.1:30303",
  "enode://2feb33b3c6c4a8f77d84a5ce44954e83e5f163e7a65f7f7a7fec499ceb0ddd76a46ef635408c513d64c076470eac86b7f2c8ae4fcd112cb28ce82c0d64ec2c94@127.0.0.1:30304",
  "enode://7b61d5ee4b44335873e6912cb5dd3e3877c860ba21417c9b9ef1f7e500a82213737d4b269046d0669fb2299a234ca03443f25fe5f706b693b3669e5c92478ade@127.0.0.1:30305"
]
```

As contas são especificadas em um array com cada conta entre aspas e separadas por vírgula:

```js
accounts-allowlist=[
  "0xb9b81ee349c3807e46bc71aa2632203c5b462032", 
  "0xb9b81ee349c3807e46bc71aa2632203c5b462034"
]
```

Os nós são especificados em uma matriz com o endereço de enode entre aspas e cada endereço de enode separado por uma vírgula:

```js
nodes-allowlist=[
  "enode://7e4ef30e9ec683f26ad76ffca5b5148fa7a6575f4cfad4eb0f52f9c3d8335f4a9b6f9e66fcc73ef95ed7a2a52784d4f372e7750ac8ae0b544309a5b391a23dd7@127.0.0.1:30303",
  "enode://2feb33b3c6c4a8f77d84a5ce44954e83e5f163e7a65f7f7a7fec499ceb0ddd76a46ef635408c513d64c076470eac86b7f2c8ae4fcd112cb28ce82c0d64ec2c94@127.0.0.1:30304",
  "enode://7b61d5ee4b44335873e6912cb5dd3e3877c860ba21417c9b9ef1f7e500a82213737d4b269046d0669fb2299a234ca03443f25fe5f706b693b3669e5c92478ade@127.0.0.1:30305"
]
```

Se o arquivo estiver em um local diferente do diretório de dados de cada nó, ao iniciar o nó, use as opções --permissions-accounts-config-file=<FILE> e --permissions-nodes-config-file= <FILE> ao iniciar cada nó. O arquivo pode ser o mesmo para contas e nós, se for configurado como mostrado acima.

Para obter mais informações, consulte a documentação do Hyperledger Besu, ["Criar uma rede com permissão"](https://besu.hyperledger.org/stable/private-networks/tutorials/permissioning).


A [permissão Onchain](https://besu.hyperledger.org/stable/private-networks/tutorials/permissioning/onchain) usa um contrato inteligente para gerenciar as permissões das contas e nós autorizados a ingressar na rede. 

O benefício de usar esse método é que a atualização das permissões ([upgrade-contracts](https://besu.hyperledger.org/stable/private-networks/tutorials/permissioning/upgrade-contracts)) é feita por meio do contrato inteligente, utilizando a funcionalidade de um blockchain para adicionar ou remover contas ou nós.