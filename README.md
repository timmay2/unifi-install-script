Unifi controller installation script to install a Unifi controller with mongodb wiredTiger write engine and other performance
optimisations as well as providing a fail proof install that should work with any Ubuntu release.

/!\ Prerequisites /!\

* Ubuntu 18.04 LTS server (64bit)
* XFS file system for best performance (if you are cloud hosting this may not be possible)

This script does the following:-

* Installs Git if not already installed
* Clones this repository
* Runs the unifiinstaller.sh shell script
* Installs libssl1.0.0
* Installs openjdk-8-jre-headless
* Adds Mongodb repository
* Installs Mongodb 3.4.24 with wiredTiger write engine
* Changes the default port for Mongodb from 27017 to 27117
* Enables Mongod deamon
* Starts Mongod deamon
* Adds the Ubiquiti stable repository
* Installs Unifi controller
* Modifies the system.properties file to support double the "default" amount of devices
* Reloads Unifi with the optimised settings file
* If all successful prints the following message to the console "*** Success! - Unifi controller is now installed :-D ***"

The settings in this script double the amount of memory allocated to the Java VM, doubles the inform threads and keep alive requests from the defaults. This should support ~2000 Unifi devices.

Copy and paste the below command into your Ubuntu server terminal to clone this repository and run the Unifi installer script.

sudo apt install -y git && git clone https://github.com/timmay2/unifi-install-script.git && sudo sh unifi-install-script/unifiinstaller.sh
