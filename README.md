## AMBEd Installer for XLXd (Debian 11 Support!)
# ambed-debian-installer N5AMD
-
This is a simple install script by N5AMD to install AMBEd, a piece of software that when combined with hardware AMBE vocoder chips and another piece of software, XLXD, can transcode digital voice modes. This script simply runs through the official install instructions found at:
https://github.com/LX3JL/xlxd/blob/master/ambed/readme
-

### How To Install:
1. Have a Debian 9, 10 or 11 x86/ARM computer ready and up to date with a 64bit CPU architecture.
2. Plug the AMBE vocoder chips into the server.
3. 
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
chmod 755 /ambed/watchdog
```
6. You can run the watchdog every 5 mins with a cron job
```sh
* */5 * * * * /ambed/./watchdog >> /ambed/watchdog.log
```

**The other parts to this install, if you need it can be found at:**

https://github.com/n5amd/Multi-Reflector-Installer

**For more information, please visit N5AMD!:**

https://n5amd.com/digital-radio-how-tos/build-digital-voice-transcoding-server/
