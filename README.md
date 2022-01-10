# AMBEd Installer for XLXd (Debain 11 Support!)

## ambed-debian-installer

This installer was orginally created by N5AMD. The script has been slightly changed with updated dependencies & updated links from FTDI. Thanks to all
the contributors on this script! The original script can be found here https://github.com/n5amd/ambed-debian-installer

To continue to use this fork please follow the instructions below:

This is a simple install script to install AMBEd, a piece of software that when combined with hardware AMBE vocoder chips and another piece of software, XLXD, can transcode digital voice modes. This script simply runs through the official install instructions found at:
https://github.com/LX3JL/xlxd/blob/master/ambed/readme


### How To Install:
1. Have a Debian 9, 10 or 11 x86/ARM computer ready and up to date with preferably a 64bit CPU.
Script works with aarch64 and Ubuntu 21.10, tried and tested on ARM. (Pi-4)!!!
3. Plug the AMBE vocoder chips into the server.
4. 
```sh
git clone https://github.com/shaymez/ambed-debian-installer
cd ambed-debian-installer
./ambed-debian-installer
```
4. Reboot after installation is complete.

### Edit AMBEd system unit for LocalHost
5. If you are running this transcoder on the same LocalHost as XLXd then there is no need to edit. If running AMBED on a remote site then you will need to include
your local IP address in the system unit file. Change the default 127.0.0.1 to your LOCAL IP etc 192.168.1........ otherwise trancoding will not work.
```sh
nano /etc/systemd/system/ambed.service
```

### To interact with AMBEd after installation:
```sh
systemctl start|stop|status|restart ambed
```
 - Installs to /ambed
 - Logs are via systemctl status

### Watchdog for AMBEd
6. Install additional tools. Assuming you are still in the ambed-debian-installer dir..
```sh
cd templates
cp watchdog /ambed/watchdog
chmod 0755 /ambed/watchdog
```
7. You can run the watchdog every 5 mins with a cron job
```sh
*/5 * * * * /ambed/./watchdog >> /ambed/watchdog.log
```

**The other parts to this install, if you need it can be found at:**

https://github.com/n5amd/Multi-Reflector-Installer

**For more information, please visit N5AMD:**

https://n5amd.com/digital-radio-how-tos/build-digital-voice-transcoding-server/
