# MVT Pegasus Spyware Checker Tutorial (Not ready Yet.)
A (simpler?) tutorial.
<br>
<br>
<b>Items Needed:</b>
* iPhone 
* USB Cable to connect iPhone with Laptop
* Laptop MacOS (to create iPhone encrypted backup)
* Laptop with Ubuntu Linux (to run the MVT Pegasus spyware checker)
* Internet access to download required software.

<b>Heads up:</b> Replace username "x", and directory "/home/x" for the ones in your system. And for UDID replace it with the iphone's 40-digit sequence of letters and numbers. Also, be sure the Ubuntu system has at least two times the space of the iPhone backup.</b>

## The Process Starts Here
<br>
<b>On Ubuntu install and run these commands:</b><br>
<code>sudo apt install python3-pip</code><br>
<code>sudo apt install libusd-1.0-0</code><br>
<code>sudo apt install sqlite3</code><br>
<code>sudo apt install git</code><br>
<code>export PATH=$PATH:~/.local/bin</code><br>
<code>mkdir -p /home/x/repos</code><br>
<code>cd /home/x/repos</code><br>
<code>git clone https://github.com/mvt-project/mvt.git</code><br>
<code>cd mvt</code><br>
<br>
<b>Install pip3. Include the dot at the end:</b><br>
<code>pip3 install .</code><br>
<br>
<b>Install the libimobiledevice utils.:</b><br>
<code>sudo apt install libimobiledevice-utils</code><br>
<br>
<b>Connect the iPhone to the Ubuntu computer.</b><br>
<b>You may need to press the "Trust" button that may show up on the iPhone.</b><br>
<br>
<b>To check if libimobiledevice-utils works. The output on the screen should show the iPhone information.</b><br>
<code>ideviceinfo</code><br>
<b>To only show your device UDID number.</b><br>
<code>ideviceinfo | grep UniqueDeviceID</code>
<br>
<b>Now on the <u>MacOS</u> computer: With the USB cable connect the iPhone. Create the iPhone backup, savind it on the Desktop area. The result should be a folder named "backup". Choose a encrypted and with a password.</b><br>
Instructions on how: https://support.apple.com/en-us/HT205220<br>
<br>
<b>Next upload the "backup" folder to the Ubuntu laptop:</b><br>
<code>rsync -HPSavx /home/x/Desktop/backup -e ssh -p 22 x@<RemoteHostIP>:/home/x/Desktop </code><br>
<br>
<b>Now back on <u>Ubuntu</u>, create the "decrypted-backup" folder. The backup needs to be decrypted to run the scan on it.:</b><br>
<code>mkdir -p /home/x/Desktop/decrypted-backup </code><br>
<br>  
<b>Decrypt the backup. Password you set up earlier is needed. Decrypted files will be in "decrypted-backup" folder.:</b><br>
<code>mvt-ios decrypt-backup -d /home/x/Desktop/backup-decrypted. /home/x/Desktop/backup</code><br>
<br>
* If the decryptor can't find the folder, add the phone's UDID as the last directory on the path syntax: /home/x/Desktop/backup/UDID <br>
Use this command to find the iPhone's UDID:<br>
<code>ideviceinfo | grep UniqueDeviceID</code><br>
<br>
<b>Finally we are ready to check the iPhone files for Pegasus traces:</b><br>
<br>
The last part of this tutorial is the easiest part, but I am running out of gas. Shall continue later on!

<br><br><br><br><br><br>









---------------------------------------------------------------------------------------
Tutorial based on: https://github.com/mvt-project/mvt <br>
TAGS: #mvt #pegasus #spyware #amnistytech #mvt-project #nso #pegasusSpyware #surveillance #spying<br>
<br>
