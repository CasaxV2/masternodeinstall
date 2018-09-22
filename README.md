# CaSaX
Shell script to install a [CaSaX Masternode](https://casax.cc/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.

***
## Installation:
```
wget https://raw.githubusercontent.com/CaSaX/masternodeinstall/master/csx.sh
sudo chmod +x csx.sh && sudo bash csx.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the CaSaX Core Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **2000** **CSX** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:

```
Alias Address Privkey TxHash Output_index
```

Your entry should look something similar to this --

```
MN1 0.0.0.0:9116 8dJmCfFcx4EHfgePaHhdSw5AC8Ss4izjBJKj9r42MZHEgo4iGpw 7573baa15732e41b5ce768aa99dc7506c63a6d89c1020975bdec3e06df142b98 0

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
startmasternode alias false MN1
```
***

## Usage:
```
Casax-cli getinfo
Casax-cli mnsync status
Casax-cli masternode status
```

Also, if you want to check/start/stop **CaSaX**, run one of the following commands as **root**:

```
systemctl status Casax #To check if CaSaX service is running
systemctl start Casax #To start CaSaX service
systemctl stop Casax #To stop CaSaX service
systemctl is-enabled Casax #To check if CaSaX service is enabled on boot
```

***
