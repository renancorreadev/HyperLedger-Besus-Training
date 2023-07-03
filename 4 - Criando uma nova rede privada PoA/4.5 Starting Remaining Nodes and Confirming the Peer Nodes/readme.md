Prerequisites:

Open a new terminal tab for each new command and leave the prior terminals running in the background.

Useful commands:

Start Node 2
besu --data-path=data --genesis-file=../cliqueGenesis.json --bootnodes=<Node-1Enode URL> --network-id 123 --p2p-port=30304 --rpc-http-enabled --rpc-http-api=ETH,NET,CLIQUE --host-allowlist="*" --rpc-http-cors-origins="all" --rpc-http-port=8546

Start Node 3
besu --data-path=data --genesis-file=../cliqueGenesis.json --bootnodes=<Node-1Enode URL> --network-id 123 --p2p-port=30305 --rpc-http-enabled --rpc-http-api=ETH,NET,CLIQUE --host-allowlist="*" --rpc-http-cors-origins="all" --rpc-http-port=8547

Confirm the private network is working:
curl -X POST --data '{"jsonrpc":"2.0","method":"net_peerCount","params":[],"id":1}' localhost:8545

To stop the private network, press Control + C in each open terminal.

For more information, please see the Hyperledger Besu Documentation, ["Using Clique (PoA) - Start Node-2"](https://besu.hyperledger.org/en/stable/Tutorials/Private-Network/Create-Private-Clique-Network/#5-start-node-2). 