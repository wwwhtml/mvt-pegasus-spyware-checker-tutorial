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

<b>Note:</b> Replace username "x", and directory "/home/x" for the ones in your system. 
Also, be sure the Ubuntu system has at least two times the space of the iPhone backup.</b>

## The Process Starts Here
<br>
<b>On Ubuntu install:</b><br>
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
<b>To check if libimobiledevice-utils is working.</b><br>
<code>ideviceinfo</code><br>
<br>
<b>Change to the home directory:</b><br>
<code>cd ~/</code></br>
</br>
<b>Now on the MacOS computer back up the iPhone files on Desktop area. When completed, the "backup" folder should be on the Desktop:</b><br>
<code>idevicebackup2 backup --full /Users/x/Desktop/</code></br>
<br>
<b>Next upload the "backup" folder to the Ubuntu laptop:</b><br>
<code>rsync -HPSavx /home/x/Desktop/backup -e ssh -p 22 x@<hostIP>:/home/x/Desktop </code><br>
<br>
<b>Back on Ubuntu create the following folder: </b><br>
<code>mkdir -p /home/x/Desktop/backup-decrypted </code><br>
<br>  
<b>Decryp the backup. Password you set up earlier is needed. Decrypted files will be in "backup-decrypted" folder.:</b><br>
<code>mvt-ios decrypt-backup -d /home/x/Desktop/backup-decrypted. /home/x/Desktop/backup</code><br>
<br>
(If the decryptor can't find the folder, add the phone's UDID (40-digit sequence of letters and numbers) as the last directory on the path. ex: /home/x/Desktop/backup/UDID)
<br>
<br>
<b>Finally we are ready to check the iPhone files for Pegasus traces:</b><br>
<br>
The last part of this tutorial is the easiest part, but I am running out of gas. Shall continue later on!

<br><br><br><br><br><br>









---------------------------------------------------------------------------------------
Tutorial based on: https://github.com/mvt-project/mvt <br>
TAGS: #mvt #pegasus #spyware #amnistytech  <br>
<br>
