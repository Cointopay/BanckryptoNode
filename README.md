## Banckrypto EURx
You will need a Tomcat environment installed to run this full node EURx servlet. Servlets are java based web containers that provide application functionality.
It will function as a full node copy, similar as how e.g. Ripple operates. The benefit is very fast and free EURx transfers via the Coinectar stack. Flexible blocksizing, tickMiner technology and is big data enabled. The backend is using MongoDB for optimal scaling. See a live interaction with one such node as this on banckrypto.com.

## API
When your users create a wallet via the front end on banckrypto.com they are immediately API enabled.
Use JSON/RPC type of connectivity utilizing the wallet name and the password and point it to https://artemis.cointopay.com/coinectar/bc or your own Banckrypto Node.
Do explorer look ups and wallet handling via the API. As easy is that.
https://documenter.getpostman.com/view/3658638/UVRDHkwm


## About the Banckrypto.com Full Node

This crypto wallet is the first hybrid blockchain bank wallet. You can transfer your EURx currency via the blockchain but you can also buy/sell trade it on cointopay.com. It is a stable currency which is being sold for one Euro per coin, however it has a limited supply of 100000000 units and can be traded on reflextrader.com. You can also import your EURx and send it via your verified bank account. You may also download this wallet and run it yourself. Welcome to the decentralized future!


## Configuration of Node
- We recommend to setup Tomcat 8.5+ on Ubuntu, but feel free to run Tomcat 8.5+ on Windows (installation and hardening is not described here, use google)
- Configure your Tomcat with domain and ssl certificate (not described here, use google)
- Download the coinectar.war you can deploy it now to your Tomcat 8.5+ environment
- Once deployed it will sync with the network and you can allow to create wallets and send and receive Banckrypto EURx

- Server Hardening: You are responsible for server hardening, you are storing private key data locally. Give this topic the attention it needs.
- Tick mining: we use a proprietary mechanism to mine Banckrypto EURx, for the time being it is centralized. Since this is a non-profit project we are open to suggestions.
- For Ubuntu linux: configure /etc/systemd/system/multi-user.target.wants/tomcat9.service and either set ProtectSystem=false or add a ReadWritePaths=/path/to/wallets config line item, otherwise tomcat cannot write to the path. Make sure tomcat user has 750 access.

## OPTIONAL USE OWN MONGODB TO STORE THE BANCKRYPTO BLOCKCHAIN LOCALLY
- Open the coinectar.war file with a zip tool (Winrar)
- Open file /WEB-INF/properties/application.properties
- Update database connection [MONGODB_CONNECTION]. Please note the coinectar only support MongoDB. (setup of mongodb is not described here, use google)
- If you change the database name in the [MONGODB_CONNECTION], then also change it here [MONGODB_NAME]
Format of the connection string is mongodb+srv://username:password@yourdomain.com/coinectar?retryWrites=true&w=majority

## Licensing statement from Cointopay.com
You may run this software for the purpose of participating in the Banckrypto EURx network. To protect the network Cointopay acts as the guardian of the software to make a statement that it is not allowed to do anything else then what it was intended for without prior consent of Cointopay.com. It is not allowed to reverse engineer or copy any of the software traits used in this software and network. One of its primary reasons to exist is act as a payment network with maximum benefit to it's users, being zero transfer fee, near instant and with limited supply. It is intended to be used in a banking like environment to enable transactions that benefits its participants. You may not cause harm to the functioning network by any means and you are envited to grow the network and it's functionality (also on github). There is currently no similar public network available. Please log an issue in case you have any questions or want to participate.

## About Cointopay.com
We are an international crypto currency payment processor, meaning that we accept payments from your customers and make the funds available to you (incl. in form of fiat currency like euro). Delivering a seamless payment experience while underlying dealing with diverse and complex blockchain technologies like EURx. P.S. If you want your own crypto currency, we can provide that for you as well, Cointopay has been a technological payment incubator since 2014!
