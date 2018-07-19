BlockChain POC using Hyperledger-Fabric, Hyperledger-Composer, Loopback REST API

A typical pre-requisite would be to download the Hyperledger Fabric first -- https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html#ubuntu

The next step would be to install and set up the dev environment
https://hyperledger.github.io/composer/latest/installing/development-tools.html

Once you have completed the above steps then the steps to start the fabric :
startup.sh

createArchive.sh ---> Creates the business network archive file(.bna) consisiting of model files(.cto), permissioning files (.acl), query files (.qry) and the smart contract logic (.js). Just these 4 files can create all the magic in creating assets, creating participants, creating transactions.

In this scenario we have the following participants : Buyer, Seller, Provider, Shipper and the Finance Company.
The assets are the Orders
Only a Buyer can create an order and approve it.
The Seller can either instruct the Shipper to sell it or order it from his third party provider if he does not have the stock.
The Provider can instruct the Shipper to Ship the products to Buyer.
The Shipper can ship the products to buyer. 
Once Buyer recieves it, he can approve a payment request or dispute the shipment and subsequently cancel the order.
The Finance Company can see all what is going on between these different participants, but he can only view all these state changes.

See in order to write all the logic of who can do what and who can see what in any other traditional existing systems would be to write lots of code. If you see in this platform how easy it is to get such complicated state, assets and transaction tracking can be achieved with a server side foot print of just 35Kbs(yes kbs, not Mbs, not Gbs).

This is why I am in love with the private permissioned blockchain using PBFT as it's consensus algorithm.
