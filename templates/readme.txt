* Watchdog to take care of reliabilty issues on AMBEd as written by LX1IQ
*
*
*************************************************
* In your XLXD instance...
* Copy xlxd to /etc.init.d/
*************************************************
* In your AMBEd instance
*copy ambed.service to /etc/systemd/system/
*copy watchdog to /ambed/
*************************************************
* xlxd executable must be in /xlxd/ folder
* ambed executable must be in /ambed/ folder
*************************************************
* possible options:
*
* #systemctl start ambed        /starts ambed
* #systemctl status ambed       /shows status of ambed
* #systemctl stop ambed         /stops ambed
* # systemctl restart ambed     /restarts ambed
*
* automatically get it to start on boot:
* #systemctl enable ambed
*
*************************************************
* If your usb port gets unresponsive and you get some persistent timeouts,
* the watchdog script restarts the ambed service.
* You can run it every 5 minutes by a cronjob.
* 
* */5 * * * * /ambed/./watchdog >> /ambed/watchdog.log
*
***************************************************
