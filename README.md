# EXCL coin masternode install script

Shell script to install a EXCLCoin Masternode on a Linux server running Ubuntu 14.04,16.04 or 18.04. Use it on your own risk.
This script will instal version 3.0.1
<hr>
<h2>VPS installation:</h2>
Login to vps as root then tyoe the following commands
<ul>
<li>wget -N https://raw.githubusercontent.com/Al3xxx19/excl-mn-install/master/excl-mn-install.sh</li>
  <li>chmod +x excl-mn-install.sh</li>
  <li>./excl-mn-install.sh</li>
</ul>
<hr>
<h2>Desktop wallet setup</h2>
After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
<ul>
<li>Open the EXCL Coin Desktop Wallet.</li>
<li>Go to RECEIVE and create a New Address: MN1</li>
<li>Send 5000 EXCL to MN1.</li>
<li>Wait for 15 confirmations.</li>
<li>Go to Tools -> "Debug console - Console"</li>
<li>Type the following command: masternode outputs</li>
<li>Go to ** Tools -> "Open Masternode Configuration File"</li>
<li>Add the following entry:</li>
<li>Alias Address Privkey TxHash Output_index</li>
<li>Alias: MN1</li>
<li>Address: VPS_IP:PORT</li>
<li>Privkey: Masternode Private Key</li>
<li>TxHash: First value from Step 6</li>
<li>Output index: Second value from Step 6</li>
<li>Save and close the file.</li>
<li>Go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab</li>
<li>Click Update status to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.</li>
<li>Open Debug Console and type:</li>
  <li>startmasternode alias false MN1</li>
</ul>
<hr>
<h2>Usage:</h2>
<ul>
<li>excl-cli mnsync status</li>
<li>excl-cli getinfo</li>
<li>excl-cli masternode status</li>
</ul>
Also, if you want to check/start/stop EXCLCoin , run one of the following commands as root:
<ul>
<li>systemctl status EXCLCoin #To check the service is running.</li>
<li>systemctl start EXCLCoin #To start EXCL service.</li>
<li>systemctl stop EXCLCoin #To stop EXCL service.</li>
<li>systemctl is-enabled EXCLCoin #To check whether EXCL service is enabled on boot or not.</li>
</ul>
