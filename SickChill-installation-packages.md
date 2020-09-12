
For many Devices there are installation packages compiled by community members. We try to collect as many as we can here. If you know about a package that isn't in the list yet, then please let us know.  

#### Some of these links are not correct. Please update this wiki if you find incorrect information

---

* [Docker](https://github.com/SickChill/SickChill/wiki/Docker)
* [Pip](https://github.com/SickChill/SickChill/wiki/Pip)
* [Windows](https://github.com/SickChill/SickChillInstaller/releases/latest)
* [Freenas](https://github.com/SickChill/SickChill/wiki/Freenas)
* [ReadyNAS](https://github.com/SickChill/SickChill/wiki/ReadyNAS)

###### Arch Linux
* https://aur.archlinux.org/packages/sickchill

---

###### Qnap 
* Download the [qpkg](https://www.qnapclub.eu/fr/qpkg/647)

---

###### Asustor
* https://www.dropbox.com/s/f016hij9ebw28qd/sickbeard-tvrage_20151227_any.apk  
Make sure you select SickChill and NOT SickRageTV.

---

###### Thecus

* http://forum.thecus.com/viewtopic.php?f=36&t=9720 (x32&x64)  
Make sure to download SickChill community Edition package, as sickragetv/sickrage is the old repo

---

###### ReadyNas
* https://github.com/Mhynlo/rn-sickchill/releases/latest  
* https://github.com/miigotu/sickchill-readynas/blob/master/sickchill_5.1.2_readynas_all.deb (UNTESTED)  

---

## Outdated Packages.!  

Those packages are not yet updated to the new URL, or are simply not maintained anymore. But as long as they are working you should be able to make the switch with manual Git commands.  


Go into the SickChill folder and do :  

```
git remote set-url origin https://github.com/SickChill/SickChill.git
git fetch origin
git reset --hard origin/master
```

In case thats not possible, you can try to switch the [dirty](https://github.com/SickChill/SickChill/wiki/SickChill-installation-packages#switching-the-dirty-way) way.

##Switching the Dirty way.  

As some installers are outdated or not maintained anymore, switching can be a little frustrating.
In most cases you can use those old packages in combination with manual Git commands to make the switch.
However in some cases this is not possible. For those there is a `Dirty` way to switch.

* 1 Run the outdated installer and install sickchill from the old Repo.
* 2 Shutdown SickChill.
* 3 Download the latest SickChill package from the [New Repo](https://github.com/SickChill/SickChill/archive/master.zip).
* 4 Unzip and overwrite the old files on your device.
* 5 Start SickChill again.

Thats it. 
However this method is meant as a last resource, and should only be used if all other methods fail.
