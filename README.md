If this [First Masternode Script](https://github.com/Revolutionary1976/sekomnsetup/blob/master/README.MD#installation) is not working use this [Second Masternode Script](https://github.com/Revolutionary1976/sekomnsetup/blob/master/README.MD#installation-1)

# SekoPayCoin
Shell script to install a [SekoPay Masternode](https://www.sekopay.com) on a Linux server running Ubuntu 16.04.
***

## Installation
```
wget https://raw.githubusercontent.com/Revolutionary1976/sekomnsetup/blob/master/install.sh
```
```
chmod +x install.sh
```
```
./install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the SekoPay Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **5000** Seko to **MN1**. You need to send all 5000 coins in one single transaction.
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
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open bytepay Core Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
startmasternode alias false <name>  # Start masternode replace <name> with your masternode alias
seko-cli getblockcount #To get blockcount
seko-cli stop #To stop masternode
./sekod -resync &  #To Resync
systemctl status condominium.service  #o check seko service status
systemctl start seko.service  #To start seko service
systemctl stop seko.service  #To stop seko service
seko-cli masternode count  #To check masternode list

```

#You Can also install using the second installation script

## Installation
```
wget -q https://raw.githubusercontent.com/Revolutionary1976/sekomnsetup/blob/master/seko-mn.sh
```
```
bash seko-mn.sh
```

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the SekoPay Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **5000** seko to **MN1**. You need to send all 5000 coins in one single transaction.
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
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open bytepay Core Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
startmasternode alias false <name>  # Start masternode replace <name> with your masternode alias
nano ~/.seko/seko.conf   #Conf File Location
sekod -daemon #Start Daemon
seko-cli getinfo #Get blockcount
seko-cli masternode status #Check Masternode Status
watch seko-cli getinfo #watch how the blocks while syncing
```
