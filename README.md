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

### To interact with AMBEd after installation:
```sh
systemctl start|stop|status|restart ambed
```
 - Installs to /ambed
 - Logs are via systemctl status

### Watchdog for AMBEd
5. Install additional tools. Assuming you are still in the ambed-debian-installer dir..
```sh
cd templates
cp watchdog /ambed/watchdog
chmod 0755 /ambed/watchdog
```
6. You can run the watchdog every 5 mins with a cron job
```sh
*/5 * * * * /ambed/./watchdog >> /ambed/watchdog.log
```

**The other parts to this install, if you need it can be found at:**

https://github.com/n5amd/Multi-Reflector-Installer

**For more information, please visit N5AMD:**

https://n5amd.com/digital-radio-how-tos/build-digital-voice-transcoding-server/
