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
1) We recommend to setup Tomcat 8.5+ on Ubuntu, but feel free to run Tomcat 8.5+ on Windows (installation and hardening is not described here, use google)
2) Configure your Tomcat with domain and ssl certificate (not described here, use google)
3) Configure MongoDB on your localhost (not described here, use google), use alternatives mentioned below "USE OWN MONGODB" or "USE FREE MONGODB.COM"
4) Download the coinectar.war right here from this github
5) Open the coinectar.war file with a zip tool (Winrar) by changing the extension to coinectar.war.zip
6) Open file /WEB-INF/properties/application.properties:
  - change the WALLETS_DIR to your own folder (e.g. /home/coinectar or C:\<your folder> for Windows)
  - MONGODB_NAME
  - MONGODB_CONNECTION (if you leave blank it will try to connect to localhost, if no mongodb available it will fail)
  - NODE_URL which is the https url it will run from
7) Save it, and change the name back to coinectar.war. You can deploy it now to your Tomcat 8.5+ environment on the /manager endpoint
8) Once deployed, run the following command to initialize the blockchain sync <NODE_URL>/coinectar/node/init
9) The blockchain will sync with the network and you can use the API as mentioned above to create wallets and send and receive Banckrypto EURx
>> Continue with deploying the front end https://github.com/Cointopay/Banckrypto if you want to make use of that

Notes:
- It will function as a full node copy, similar as how e.g. Ripple operates. The benefit is very fast and free EURx transfers via the Coinectar stack. Flexible blocksizing, tickMiner technology and is big data enabled. The backend is using MongoDB for optimal scaling. See a live interaction with one such node as this on banckrypto.com.
- Server Hardening: You are responsible for server hardening/security, you are storing private keys data locally. Give this topic the attention it needs.
- Tick mining: we use a proprietary mechanism to mine Banckrypto EURx dynamic blocks. For for the time being it is centralized, benefit is zero transaction fees.
- For Ubuntu linux 20.x: configure /etc/systemd/system/multi-user.target.wants/tomcat9.service and either set ProtectSystem=false or add a ReadWritePaths=/path/to/wallets config line item, otherwise tomcat cannot write to the path. Dont forget: sudo systemctl daemon-reload ; sudo service tomcat9 restart (Make sure tomcat user has 750 access rights on entire folder structure). E.g. mkdir /mnt/sda1/coinectar ; chown tomcat:tomcat /mnt/ ; chown tomcat:tomcat /mnt/sda1/ ; chown tomcat:tomcat /mnt/sda1/coinectar). Use journalctl -u tomcat9 -f -n 1000 to see the logs.

## USE OWN MONGODB TO STORE THE BANCKRYPTO BLOCKCHAIN LOCALLY
** If you are not configuring the application mongodb_connection, then the application will assume the connection is to the localhost (mongodb://localhost:27017/coinectar?retryWrites=false), your application cannot run without MongoDB!! You have to install it to make this work.
** We recommend to use mongodb.com they have a free tier use that is easy to setup the connection string, but don't forget to whitelist the ip your are connecting from (database access). See "USE FREE MONGODB.COM" section below.

- Open the coinectar.war file with a zip tool (Winrar)
- Open file /WEB-INF/properties/application.properties
- Update database connection [MONGODB_CONNECTION]. Please note the coinectar only support MongoDB. (setup of your own mongodb is not described here, use google)
- If you change the database name in the [MONGODB_CONNECTION], then also change it here [MONGODB_NAME]
Format of the connection string is mongodb+srv://username:password@yourdomain.com/coinectar?retryWrites=true&w=majority

## USE FREE MONGODB.COM TO STORE THE BANCKRYPTO BLOCKCHAIN
1) create account at mongodb.com
2) Go to Databases
3) Browse Collections
4) Create Database (enter database name "coinectar" and collection name "addresses"), rest will be created automatically
5) Go to Database Access tab, Add new database user
6) Enter username cointopay and select password (use long password or autogenerate it)
7) Add a specific privilege "readWrite" @ coinectar Collection*
8) Remove the built-in role "read and write to any database" by clicking on the thrash icon
9) You can restrict to specific current Clusters if you have multiple Clusters in your account (extra security)
10) Go to menu Network access and whitelist the ip on "IP Access list" that you are connecting from
11) Now go back to Databases in menu, click connect, select Driver Java and Version latest, copy the connection string
12) Construct the string that you need in the application.properties:
MONGODB_CONNECTION=mongodb+srv://<username>:<password>@<replace this to your>.mongodb.net/<yourdbname>?retryWrites=true&w=majority

## Licensing statement from Cointopay.com
You may run this software for the purpose of participating in the Banckrypto EURx network. To protect the network Cointopay acts as the guardian of the software to make a statement that it is not allowed to do anything else then what it was intended for without prior consent of Cointopay.com. It is not allowed to reverse engineer or copy any of the software traits used in this software and network. One of its primary reasons to exist is act as a payment network with maximum benefit to it's users, being zero transfer fee, near instant and with limited supply. It is intended to be used in a banking like environment to enable transactions that benefits its participants. You may not cause harm to the functioning network by any means and you are envited to grow the network and it's functionality (also on github). There is currently no similar public network available. Please log an issue in case you have any questions or want to participate.

## About Cointopay.com
We are an international crypto currency payment processor, meaning that we accept payments from your customers and make the funds available to you (incl. in form of fiat currency like euro). Delivering a seamless payment experience while underlying dealing with diverse and complex blockchain technologies like EURx. P.S. If you want your own crypto currency, we can provide that for you as well, Cointopay has been a technological payment incubator since 2014!
