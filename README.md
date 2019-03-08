# BlastX MN Script
Shell script to install a [BlastX Masternode](https://www.blastexchange.com/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.

***
## Installation:
```
git clone https://github.com/BlastX-Core/BlastX-MN-Install
cd BlastX-MN-Install
bash blastx-mn-install.sh

```
***
## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the BlastX Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **10000** **BLAST** to **MN1**.
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
12. Open **Debug Console** and type:
```
startmasternode "alias" "0" "MN1"
```
***

## Usage:
```
blastx-cli getinfo
blastx-cli mnsync status
blastx-cli masternode status
```
Also, if you want to check/start/stop **blastx** , run one of the following commands as **root**:

**Ubuntu 16.04**:
```
systemctl status blastx #To check the service is running.
systemctl start blastx #To start BlastX service.
systemctl stop blastx #To stop BlastX service.
systemctl is-enabled blastx #To check whether BlastX service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/blastx start #To start BlastX service
/etc/init.d/blastx stop #To stop BlastX service
/etc/init.d/blastx restart #To restart BlastX service
```
***
