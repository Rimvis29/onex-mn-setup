
ONEX.NETWORK MASTERNODE SETUP
Shell script to install a Onex Coin Masternode on a Linux server running Ubuntu 16.04. Use it on your own risk.

Installation 
$ sudo wget -q https://raw.githubusercontent.com/Rimvis29/onex-mn-setup/master/mn_install.sh
$ sudo bash mn_install.sh
Desktop wallet setup
After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:

Open the Onex coin Desktop Wallet.
Go to RECEIVE and create a New Address: MN1
Send 5000 ONEX to MN1. You need to send all 5000 coins in one single transaction.
Wait for 15 confirmations.
Go to Help -> "Debug Window - Console"
Type the following command: masternode genkey
Copy and paste your Privkey in linux vps.
Type the following command: masternode outputs
Go to Tools -> "Open Masternode Configuration File"
Add the following entry:
Alias Address Privkey TxHash Output_index
Alias: MN1
Address: VPS_IP:18291
Privkey: Masternode Private Key
TxHash: First value from Step 7
Output index: Second value from Step 7
Save and close the file.
Go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab
Click Update status to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
Select your MN and click Start Alias to start it.
Alternatively, open Debug Console and type:
masternode start-alias "MN1"
Login to your VPS and check your masternode status by running the following command:.

onex-cli masternode status
onex-cli mnsync status 
onex-cli getinfo
