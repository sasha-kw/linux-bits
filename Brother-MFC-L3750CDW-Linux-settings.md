### Environment
OS: Ububtu 20.04 LTS
Printer: Brother MFC-L3750CDW

**There is no need to use the 3rd party Brother driver.**

### cups setup

0. install cups package and make sure `cupsd` is running (`apt install cups && systemctl enable cups && systemctl start cups`)
1. go to http://localhost:631
2. add a printer
3. add as "Networked LPD/LPR printer"
4. enter the host as `lpd://<PRINTERIP>:515/PASSTHRU` (e.g. 192.168.XXX.XXX)
5. select the driver as `Generic PCL Color Laser - CUPS+Gutenprint v5.3.3` (`apt install printer-driver-gutenprint` if missing, although this should come with cups)
6. add the printer and set it as default
7. print a test page

### cups settings reference

```
Description:    Generic
Location:
Driver: Generic PCL Color Laser - CUPS+Gutenprint v5.3.3 (color, 2-sided printing)
Connection:     lpd://192.168.XX.XXX:515/PASSTHRU
Defaults:       job-sheets=none, none media=iso_a4_210x297mm sides=one-sided
```
