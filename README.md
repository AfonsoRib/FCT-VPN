# VPN FCT - Linux
This guide intends to allow the use of FCT's VPN on Linux

## Compatibility
 * Tested and working on Ubuntu 19.10 with Firefox 73 installed
 * Should work for all Ubuntu distros (Ubuntu, Kubuntu, Lubuntu, Xubuntu, Pop Os!, Elementary OS, Linux Mint, ...)

## Prerequisites

### Java

You need to have Oracle JRE or Oracle OpenJDK installed, to check if it is, open a terminal window (press <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>T</kbd> or search for it in the application menu) and type
 ```
  java -version
  ```
  if your output looks anything like this:
  ```
  openjdk version "1.8.0_242"
  OpenJDK Runtime Environment (build 1.8.0_242-8u242-b08-0ubuntu3~19.10-b08)
  OpenJDK 64-Bit Server VM (build 25.242-b08, mixed mode)
  ```
  Java is installed. 
  
  If it looks like this:
  ```
    The program ‘java’ can be found in the following packages:
    * default-jre
    * gcj-4.6-jre-headless
    * openjdk-6-jre-headless
    * gcj-4.5-jre-headless
    * openjdk-7-jre-headless
    Try: sudo apt-get install
```
  Type in the terminal:

  ```
  sudo apt install default-jre
  ```
  Check if it was correctly installed by typing again:
  ```
  java -version
  ```
  The output should now look like the one presented previously.

 ### Firefox

 To check if you have Firefox installed either look for it in the applications menu or type in terminal:

 ```
  firefox
  ```
  if you don't, type:

  ```
  sudo apt install firefox
  ```
### Libraries required by the VPN
 
 To install them type in the terminal:
 
  ```
  sudo apt-get install libpam0g:i386 && sudo apt-get install libx11-6:i386 && sudo apt-get install libstdc++6:i386 && sudo apt-get install libstdc++5:i386 && sudo apt-get install libnss3-tools
  ```

### SSL network extender
 Download it from the vpn's website: https://vpn.fct.unl.pt/sslvpn/SNX/INSTALL/snx_install.sh
 <br/>Save it in an easy to reach location (ie. Desktop, Documents, Downloads)
 <br/>Open a terminal window and type:
 ```
  cd ~/(location where it was saved (ie. Documents, Downloads, Desktop)) && sudo bash ./snx_install.sh
```
Afterwards reboot your computer or VM.

## Finishing setup

 * Open Firefox and go to https://vpn.fct.unl.pt/  
 * Sign-in using your CLIP credentials
 * You should see a window like this ![window](https://github.com/Diogo-Paulico/FCT-VPN/blob/master/1VPN.png)
 * Press <kbd>Connect</kbd>
 * A window like this should pop up ![window](https://github.com/Diogo-Paulico/FCT-VPN/blob/master/2VPN.png)
 * Press "Click here to download the Mobile Access Portal Agent."
 * Save it in an easy to reach location (ie. Desktop, Documents, Downloads)
 * Open a terminal window and type:
    ```
     cd ~/(location where it was saved (ie. Documents, Downloads, Desktop)) && sudo bash ./cshell_install.sh
    ```
 * Close all Firefox windows when it asks
 * Once it finishes installing you can close the terminal and open Firefox
 * Go to https://localhost:14186/id/
 * You should see this ![window](https://github.com/Diogo-Paulico/FCT-VPN/blob/master/3VPN.png)
 * Press Advanced > Accept the risk and proceed
 * You should see a random string of digits.
 * Restart Firefox and open https://vpn.fct.unl.pt/
 * Login and press connect, you should now be connected. 
 * Attempt to access Mooshak:
    http://mooshak.di.fct.unl.pt/~mooshak/
    OR
    http://193.136.122.90/~mooshak/
   
   The first one should take a while, it's normal.

## Normal access:
 After all these steps are done all you have to do to use it on a daily basis is access the VPN's website, login, click connect and you should be able to acess Mooshak from outside the FCT

 ## Known issues:
  * Can only acess Mooshak, none other of the FCT's websites seem to work
