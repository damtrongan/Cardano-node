relay
============

These are docker-compose files for building Cardano node in preprod.


### Usage
```
apt-get update && apt-get upgrade -y && apt-get install docker-compose -y
mkdir -p /docker && cd /docker
git clone https://github.com/damtrongan/Cardano-node
mkdir -p /docker/relay/node-config
cd ./Cardano-node/03_Docker/relay/node-config

curl -O -J "https://book.play.dev.cardano.org/environments/preview/{config,db-sync-config,submit-api-config,topology,byron-genesis,shelley-genesis,alonzo-genesis,conway-genesis}.json"
cd ..
docker-compose up -d --build
```


Get the tip:
```
docker exec -ti preprod-relay /usr/local/bin/cardano-cli query tip --testnet-magic 2
```
[Testnet-magic docs](https://developers.cardano.org/docs/get-started/cardano-cli/get-started/)


Mainnet
export CARDANO_NODE_NETWORK_ID=mainnet 

Pre-production testnet
export CARDANO_NODE_NETWORK_ID=1

Preview testnet
export CARDANO_NODE_NETWORK_ID=2

SanchoNet testnet
export CARDANO_NODE_NETWORK_ID=4