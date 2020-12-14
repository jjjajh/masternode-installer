► STEP 1 : CREATE SWAP FILE AND ALLOWING PORT 7070 ON FIREWALL [Copy paste below code as it is and hit enter]

dd if=/dev/zero of=/mnt/myswap.swap bs=1M count=4000 && mkswap /mnt/myswap.swap && chmod 0600 /mnt/myswap.swap && swapon /mnt/myswap.swap && ufw allow 22/tcp && ufw limit 22/tcp && ufw allow 2171/tcp && ufw logging on && ufw --force enable

► STEP 2 : INSTALL DEPENDENCIES REQUIRED [Copy paste below code as it is and hit enter]

apt-get update -y && apt-get upgrade -y && apt-get install git -y && apt-get install libzmq3-dev && apt-get install build-essential libssl-dev libboost-all-dev libqrencode-dev pkg-config libminiupnpc-dev qt5-default qttools5-dev-tools libgmp3-dev -y && add-apt-repository ppa:bitcoin/bitcoin -y && apt-get update -y && apt-get install libdb4.8-dev libdb4.8++-dev -y && apt-get install autoconf -y && apt-get install build-essential libtool autotools-dev pkg-config libssl-dev libboost-all-dev autoconf automake -y && apt-get install libzmq3-dev libminiupnpc-dev libssl-dev libevent-dev -y && apt-get install libgmp-dev -y && apt-get install openssl -y && apt-get update -y && apt-get install git build-essential -y && sudo apt-get install aptitude -y && sudo aptitude install libdb4.8++-dev -y && apt-get install git -y && sudo apt-get install software-properties-common python-software-properties -y && sudo add-apt-repository ppa:git-core/ppa && sudo apt-get update -y && sudo apt-get install git -y

► STEP 3 : CLONE INSTALLATION SCRIPT FROM GIT HUB

git clone https://github.com/jjjajh/masternode-installer.git

► STEP 4 : ENTER INTO FOLDER CLONED FROM GITHUB

cd masternode-installer

► STEP 5 : GIVE READ AND WRITE PERMISSION TO DOWNLOADED MN SCRYPT FILE

chmod 755 masternode-installer.sh

► STEP 6 : RUNNING AUTO INSTALL MASTERNODE SCRYPT

bash masternode-installer.sh

Now wait for some time for configuration and installation to get complete. 

► STEP 7 : ENTER YOUR MASTERNODE PRIVATE KEY GENERATED FROM LOCAL WALLET

THATS IT , YOUR THATSTHELABOR MASTERNODE IS NOW RUNNING ON VPS. SIMPLY CONFIGURE YOUR LOCAL WALLET FOR MASTERNODE AND START.

Desktop wallet setup After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet

Open the THATSTHELABOR Wallet.</br>
Go to RECEIVE and create a New Address: MN1</br>
Send 10000000 TTL to MN1.</br>
Wait for confirmations.</br>
Go to Tools -> "Debug console - Console"</br>
Type the following command: masternode outputs</br>
Go to ** Tools -> "Open Masternode Configuration File" ► Add the following entry: </br>
• Alias Address Privkey TxHash Output_index </br>
• Alias: MN1 </br>
• Address: VPS_IP:7070 </br>
• Privkey: Masternode Private Key </br>
• TxHash: First value from Step 6 </br>
• Output index: Second value from Step 6 It can be 0 or 1</br>
SAVE and exit the Wallet.</br>
Open THATSTHELABOR Wallet, go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab</br>
Click Update status to see your node. If it is not shown, close the wallet and start it again.</br>
Click Start All or Start Alias</br>
If then also not starting then click on >tools>debug console> Type: startmasternode alias false "name of your MN alias"
