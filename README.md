# ONEX
Shell script to install a [ONEX Coin Masternode](http://onex.network/) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/Rimvis29/onex-mn-setup/master/mn_install.sh

$ sudo bash mn_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the ONEX Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **5000** ONEX to **MN1**. You need to send all 5000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode genkey**  copy and paste your Privkey in linux vps.
7. Type the following command: **masternode outputs**
8. Go to  **Tools -> "Open Masternode Configuration File"**
9. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:18291**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 7**
* Output index:  **Second value from Step 7**
10. Save and close the file.
11. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
12. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
13. Select your MN and click **Start Alias** to start it.
14. Alternatively, open **Debug Console** and type:
```
masternode start-alias "MN1"
```
15. Login to your VPS and check your masternode status by running the following command:.
```
onex-cli masternode status
onex-cli blockcount
MAKE SURE YOUR VPS WALLET FULLY SYNCHRONIZED BLOCKS.
```
***

## Usage:
```
onex-cli mnsync status
onex-cli masternode status  
onex-cli getinfo
```
Also, if you onex to check/start/stop **ONEX**, run one of the following commands as **root**:

```
systemctl status ONEX #To check if ONEX service is running  
systemctl start ONEX #To start ONEX service  
systemctl stop ONEX #To stop ONEX service  
systemctl is-enabled ONEX #To check if ONEX service is enabled on boot  
```  
***
