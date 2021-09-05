
# MVT Pegasus Spyware Checker Tutorial (Not ready Yet.)
A (simpler?) tutorial.
<br>
<br>
Needed:
* iPhone 
* USB Cable to connect iPhone with Laptop
* Laptop MacOS (to create iPhone encrypted backup)
* Laptop with Ubuntu Linux (to run the MVT Pegasus spyware checker)
* Internet access to download required software.
* Patience, because there is a lot of waiting.

Heads up: Replace username "x", and directory "/home/x" for the ones in your system. And for UDID replace it with the iphone's 40-digit sequence of letters and numbers. Also, be sure the Ubuntu system has at least two times the space of the iPhone backup.

## The Process Starts Here
<br>
On <b>Ubuntu</b> run these commands, one line at the time:<br>
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
For the following command, please include the dot at the end of the line:<br>
<code>pip3 install .</code><br>
<br>
Now, still in <b>Ubuntu</b>, install the libimobiledevice utils:<br>
<code>sudo apt install libimobiledevice-utils</code><br>
<br>
To check if libimobiledevice-utils works, connect the iPhone  to the <b>Ubuntu</b> computer.<br>
If the first time connecting the iPhone, make sure the phone the phone is unlocked and that "Trust" button be pressed, so the connection between the iPhone and Ubuntu be allowed. Then run this command:<br>
<code>ideviceinfo</code><br>
The output of the above command should have shown the iPhone's information.<br>
<br>
Using the USB cable connect the iPhone to the <b>MacOS</b> computer. Create the iPhone backup, savind it on the Desktop area. The result should be a folder named "backup". Choose a encrypted and with a password.<br>
Instructions on how: https://support.apple.com/en-us/HT205220<br>
<br>
Next upload the "backup" folder to the <b>Ubuntu</b> laptop:<br>
<code>rsync -HPSavx /home/x/Desktop/backup -e ssh -p 22 x@<RemoteHostIP>:/home/x/Desktop </code><br>
<br>
Now back on <b>Ubuntu</b> user's Desktop area create a folder named: "decrypted-backup".<br> 
<code>mkdir -p /home/x/Desktop/decrypted-backup </code><br>
<br>  
Now let's decrypt the backup. The password set during the backup process is now needed. When done, the decrypted files will be in "decrypted-backup" folder.:<br>
<code>mvt-ios decrypt-backup -d /home/x/Desktop/backup-decrypted. /home/x/Desktop/backup</code><br>
<br>
* If the decryptor can't find the source folder, add the iPhone's UDID number as the last directory on the path, syntax: /home/x/Desktop/backup/UDID. 
Use this command to find the iPhone's UDID:<br>
<code>ideviceinfo | grep UniqueDeviceID</code><br>
<br>
Finally we are ready to check the iPhone files for Pegasus spyware traces:<br>
<br>
<i>The last part of this tutorial is the easiest part, but I am running out of gas. Shall continue later on!</i>

<br><br>




---------------------------------------------------------------------------------------
Tutorial based on: https://github.com/mvt-project/mvt <br>
TAGS: #MobileVerificationToolkit #mvt #pegasus #spyware #amnistytech #mvt-project #nso #pegasusSpyware #surveillance #spying<br>
<br>
