Quando o início rápido estiver funcionando, você obterá a seguinte saída, que lista os pontos de extremidade nos quais você pode fazer solicitações ou acessar ferramentas adicionais:


*************************************
Quorum Dev Quickstart
*************************************
Setting up the index patterns in kibana ...
----------------------------------
List endpoints and services
----------------------------------
JSON-RPC HTTP service endpoint      : http://localhost:8545
JSON-RPC WebSocket service endpoint : ws://localhost:8546
Web block explorer address          : http://localhost:25000/
Prometheus address                  : http://localhost:9090/graph
Grafana address                     : http://localhost:3000/d/XE4V0WGZz/besu-overview?orgId=1&refresh=10s&from=now-30m&to=now&var-system=All
Collated logs using Kibana endpoint : http://localhost:5601/app/kibana#/discover

For more information on the endpoints and services, refer to README.md in the installation directory.
****************************************************************



Existem duas ferramentas de monitoramento incluídas no Quickstart, Prometheus e Granfana. 

O Prometheus é uma ferramenta de monitoramento de código aberto que extrai dados dos serviços aos quais está conectado - como nós, bancos de dados, validadores, servidores etc., e permite que esses dados desses serviços sejam usados em alertas e notificações. 

Por exemplo, se o uso de memória de um determinado nó em sua rede exceder um limite definido, o Prometheus poderá rastreá-lo e alertá-lo para que você tome uma ação apropriada para garantir que sua rede continue funcionando corretamente. Em caso de falha, o Prometheus fornece os dados dos vários serviços para permitir a resolução do problema. O Prometheus extrai os dados e os armazena em um banco de dados e, em seguida, permite que você ou uma ferramenta de visualização de dados consulte esses dados. Você tem acesso ao Prometheus em http://localhost:9090/graph (você pode digitar isso em seu navegador).

O Prometheus tem uma integração com o [Grafana](https://grafana.com/) - uma plataforma de observabilidade que recebe dados - neste caso de nosso blockchain privado via Prometheus - e exibe as saídas como visualizações. Isso nos permite entender o que está ocorrendo em nossa rede privada ao longo do tempo. O Quickstart gerencia a conexão dos dados do Prometheus com painéis pré-construídos no Grafana. Você tem acesso ao Grafana aqui, as métricas do Prometheus serão exibidas em um painel do Grafana, fornecendo-nos as métricas em formato tabular e gráfico.


Para obter mais informações, consulte a documentação do Hyperledger Besu, ["Developer Quickstart"](https://besu.hyperledger.org/en/stable/Tutorials/Developer-Quickstart/).