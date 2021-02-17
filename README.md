Digicoincore Node
============

A Digicoin full node for building applications and services with Node.js. A node is extensible and can be configured to run additional services.

## Getting Started

1. Install nvm https://github.com/creationix/nvm  

    ```bash
    nvm i v6
    nvm use v6
    ```  
2. Install mongo https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/  

3. Install digicoin-bitcore https://github.com/digiassetindonesia/digicoin-bitcore - with ZMQ ! 

    ```bash
    # with ZMQ
    sudo apt-get install libzmq3-dev 
    ```  
4. Install digicoincore-node  

    ```bash
    npm i https://github.com/digiassetindonesia/digicoincore-node.git#master

    $(npm bin)/digicoincore-node create mynode

    cd mynode

    ```  
5. Edit digicoincore-node.json  

    ```json
    {
      "network": "livenet",
      "port": 3001,
      "services": [
	    "digicoind",
        "web"
      ],
      "servicesConfig": {
        "digicoind": {
          "spawn": {
            "datadir": "/home/user/.digicoin",
            "exec": "/home/user/digicoin-bitcore/src/digicoind"
          }
        }
      }
	}
    ```  
6. Edit digicoin.conf  

    ```
    server=1
    whitelist=127.0.0.1
    txindex=1
    addressindex=1
    timestampindex=1
    spentindex=1
    zmqpubrawtx=tcp://127.0.0.1:28332
    zmqpubhashblock=tcp://127.0.0.1:28332
    rpcallowip=127.0.0.1
    rpcuser=user
    rpcpassword=password
    rpcport=18332
    reindex=1
    gen=0
    addrindex=1
    logevents=1
    ```  
7. Run Node  

    ```
    $(npm bin)/digicoincore-node start
    ```  

## Add-on Services

There are several add-on services available to extend the functionality of Digicoincore:

- [Digicoin Insight API](https://github.com/digiassetindonesia/insight-api)
- [Digicoin Explorer](https://github.com/digiassetindonesia/digicoin-explorer)

## Contributing



## License
