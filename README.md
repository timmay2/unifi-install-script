Unifi controller installation script to install a Unifi controller with mongodb wiredTiger write engine and other performance
optimisations as well as providing a fail proof install that should work with any Ubuntu release.

The settings in this script double the amount of memory allocated to the Java VM, doubles the inform threads and keep alive requests from
the defaults.

You should adjust the settings accordingly for your set-up and server specification.

unifi.xmx=2048\nunifi.xms=2048\nunifi.G1GC.enabled=true\ninform.num_thread=400\ninform.max_keep_alive_requests=200

Simple run the below command to clone this repository and run the Unifi installer script if you are not makeing any other changes to 
these settings.

sudo apt install -y git && git clone https://github.com/timmay2/unifi-install-script.git && sudo sh unifi-install-script/unifiinstaller.sh
