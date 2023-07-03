Iniciando o Besu e conectando-se a redes alternativas

Besu pode ser usado para sincronizar com a rede principal Ethereum, as redes de teste Ethereum (especificamente Ropsten, Rinkeby ou Goerli), bem como localmente em seu computador. Isso é feito usando os sinalizadores --network e --data-path:

besu --network=<network> --data-path=<path>/<networkdata-path>

Com a rede à qual você está se conectando, substitua <network> e o local onde os dados do blockchain são armazenados vai nos campos <path>/<networkdata-path>. Nos comandos úteis abaixo, você poderá ver os sinalizadores que pode usar para se conectar ao Ropsten, Rinkeby e Goerli.


Comandos úteis:

Conecte-se a Ropsten
besu --network=ropsten --data-path=<caminho>/<ropstendata-path>
Conecte-se a Rinkeby
besu --network=rinkeby --data-path=<path>/<rinkebydata-path>
Conecte-se a Goerli
besu --network=goerli --data-path=<caminho>/<goerlidata-path>
Para obter mais informações, consulte a documentação do Hyperledger Besu, "Iniciando o Hyperledger Besu".

https://besu.hyperledger.org/en/stable/HowTo/Get-Started/Starting-node/



en:

Besu can be used to sync with Ethereum mainnet, the Ethereum testnets (specifically Ropsten, Rinkeby, or Goerli), as well as locally on your computer. This is done using the flags --network and --data-path:

besu --network=<network> --data-path=<path>/<networkdata-path>

With the network you are connecting to replacing <network> and the location where the blockchain data is stored goes in the <path>/<networkdata-path> fields. In the useful commands below, you will be able to see the flags you can use to connect to the Ropsten, Rinkeby, and Goerli.


Useful commands:

Connect to Ropsten
besu --network=ropsten --data-path=<path>/<ropstendata-path>
Connect to Rinkeby
besu --network=rinkeby --data-path=<path>/<rinkebydata-path>
Connect to Goerli
besu --network=goerli --data-path=<path>/<goerlidata-path>
For more information, please see the Hyperledger Besu Documentation, "Starting Hyperledger Besu".