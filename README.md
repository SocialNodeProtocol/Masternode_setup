## Setup the Social Node Masternode



### 1. VPS

You can but VPS in [vultr.com](https://www.vultr.com/?ref=7230669)

##### Requirements

- Ubuntu v16.04.x VPS with 1 CPU / 1GB MEM
- ssh client

1. login into your vps as root

2. run this command and copy the **masternodeprivatekey**

   ```
   git clone https://github.com/SocialNodeProtocol/Masternode_setup.git
   cd Masternode_setup && bash installMN.sh
   ```
   
   Enter "y";
   
   ![](https://github.com/SocialNodeProtocol/Masternode_setup/blob/master/images/step1.png)
   
   
   
   Just Enter:
   
   ![](https://github.com/SocialNodeProtocol/Masternode_setup/blob/master/images/step2.png)
   
   
   
   Finally you will get this:
   
   ![](https://github.com/SocialNodeProtocol/Masternode_setup/blob/master/images/step3.png)

### 2. Wallet

1. Tools > Debug Console input this command and you will get a address:

2. ```
   getnewaddress
   ```

2. send **1000 SMN** to this address

3. wait 15 confirms of transaction

4. Tools > Debug Console input this command you will get the **collateral_output_txid  and collateral_output_index**

   ```
   masternode outputs
   ```
   
6. Setting > Open masternode configuration file add:

   ```
   mn1 VPS_IP:32301 masternodeprivatekey collateral_output_txid collateral_output_index
   ```

7. restart wallet

8. Tools > Debug Console input this command

9. ```
   masternode start-alias mn1
   ```
