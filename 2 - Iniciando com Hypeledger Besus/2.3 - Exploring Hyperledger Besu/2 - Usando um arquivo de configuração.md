


Nas duas últimas lições, mostramos como um comando, besu, nos permite iniciar uma rede. Também vimos como opções como --network= e --data-path= nos permitem alterar a rede à qual nos conectamos e o diretório onde os dados do blockchain são armazenados, respectivamente.

Opções e subcomandos podem ser armazenados no que chamamos de arquivo de configuração ou arquivo de configuração. Este arquivo permite as especificações dos parâmetros iniciais do Besu, e nos dá um arquivo onde podemos salvar esses parâmetros caso desejemos reutilizá-los.

Os arquivos de configuração estão no formato TOML. Um arquivo de configuração de exemplo é mostrado abaixo. Os comentários são exibidos após um símbolo # e fornecem contexto sobre o que cada linha faz.


```
# Valid TOML config file
data-path="~/besudata"
# This is the datapath where the blockchain data will be stored

# Network
bootnodes=["enode://001@123:4567", "enode://002@123:4567", "enode://003@123:4567"]
# In a private network, an enode URL is the identifier for a node and
# allows for the bootnodes to discover each other as they start up. In
# this example, there are three bootnodes stipulated for this network

p2p-host="1.2.3.4"
# Stipulates the advertised host that can be used to access the node
# from outside the network in Peer to Peer communication
p2p-port=1234
#
max-peers=42
# The maximum number of peer to peer connections this network can
# establish

rpc-http-host="5.6.7.8"
# Specifies the host on which HTTP JSON-RPC listens
rpc-http-port=5678
# The HTTP JSON-RPC listening port (TCP)

rpc-ws-host="9.10.11.12"
# The host for Websocket WS-RPC to listen on
rpc-ws-port=9101
# The Websockets JSON-RPC listening port (TCP)

genesis-file="~/genesis.json"
# Path to the custom genesis file. The next lesson will explain how to
# create a genesis file and what is contained in the genesis file

miner-enabled=true
# This option enables mining when the node is started. The type of
# consensus mechanism will be stipulated in the genesis file

miner-coinbase="0xfe3b557e8fb62b89f4916b721be55ceb828dbd73"
# miner-coinbase provides the account to which mining rewards will be
# paid for this blockchain

```


Alguns pontos-chave para entender. Dentro do arquivo de configuração, cada opção não terá os traços iniciais que estariam presentes se essas opções ou subcomandos fossem chamados diretamente da linha de comando. Certifique-se de que o formato do arquivo de configuração exibido acima seja seguido. Os comentários são opcionais, mas podem ajudar a entender como o arquivo de configuração é configurado, o que é especialmente útil se você estiver tentando lembrar a configuração de uma rede específica.

O arquivo de configuração deve ser salvo como config.toml.

Para iniciar uma rede usando o arquivo de configuração, vá para a linha de comando e use o comando besu com a opção --config-file=<caminho do arquivo>/config.toml.


Por exemplo, isso ficaria assim:

besu --config-file=/home/me/me_node/config.toml

Para ver todas as opções que podem ser usadas no arquivo de configuração ou por meio da interface de linha de comando, consulte o artigo ["Hyperledger Besu Command Line"](https://besu.hyperledger.org/en/stable/Reference/CLI/CLI-Syntax/).


https://besu.hyperledger.org/en/stable/HowTo/Configure/Using-Configuration-File/