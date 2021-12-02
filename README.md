## Banckrypto EURx
You will need a Tomcat environment installed to run this servlet. It will function as a full node copy, similar as how e.g. Ripple operates.
The benefit is very fast and free EURx transfers via Coinectar. Flexible blocksizing and proprietary tickMiner technology and is big data enabled.
The backend is using MongoDB for optimal scaling.

## API
When your users create a wallet via the front end on banckrypto.com they are immediately API enabled.
Use JSON/RPC type of connectivity utilizing the wallet name and the password and point it to https://artemis.cointopay.com/coinectar/bc or your own Banckrypto Node.
Do explorer look ups and wallet handling via the API. As easy is that.


## About the Banckrypto.com Full Node

This crypto wallet is the first hybrid blockchain bank wallet. You can transfer your EURx currency via the blockchain but you can also buy/sell trade it on cointopay.com. It is a stable currency which is being sold for one Euro per coin, however it has a limited supply of 100000000 units and can be traded on reflextrader.com. You can also import your EURx and send it via your verified bank account. You may also download this wallet and run it yourself. Welcome to the decentralized future!


## Configuration of Node

- Open the coinectar.war file with a zip tool (Winrar)
- Open file /WEB-INF/properties/application.properties
- Update database connection [MONGODB_CONNECTION]. Please note the coinectar only support MongoDB.
- If you change the database name in the [MONGODB_CONNECTION], then also change it here [MONGODB_NAME]
