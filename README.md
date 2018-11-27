# LRMcoin
Shell script to install a [LRMcoin Masternode](https://www.lrmcoin.cc/) on a Linux server running Ubuntu 14.04, 16.04 or 18.04. Use it on your own risk.

***
## Installation:
```
git clone https://github.com/lrmproject/lrm-install/
cd lrm-install
bash lrm-install.sh
```
***
## Update wallet to latest version:
```
cd ~/lrm-install/
git pull
bash lrm-update.sh
```
***
## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the LRMcoin Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **LRMcoin** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Next, go to our **Discord channel** for detailed instructions: https://discord.gg/UE6KJmW
***

## Usage:
```
lrmcoin-cli getinfo
lrmcoin-cli mnsync status
lrmcoin-cli masternode status
```
Also, if you want to check/start/stop **LRMcoin** , run one of the following commands as **root**:

**Ubuntu 16.04 or 18.04**:
```
systemctl status LRMcoin #To check the service is running.
systemctl start LRMcoin #To start LRMcoin service.
systemctl stop LRMcoin #To stop LRMcoin service.
systemctl is-enabled LRMcoin #To check whetether LRMcoin service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/LRMcoin start #To start LRMcoin service
/etc/init.d/LRMcoin stop #To stop LRMcoin service
/etc/init.d/LRMcoin restart #To restart LRMcoin service
```
***
