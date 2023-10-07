For many Devices there are installation packages compiled by community members. We try to collect as many as we can here. If you know about a package that isn't in the list yet, then please let us know.

#### Some of these links are not correct. Please update this wiki if you find incorrect information

---

- [Docker](Docker.md)
- [Pip](Pip.md)
- [Windows](https://github.com/SickChill/SickChillInstaller/releases/latest)
- [Freenas](Freenas.md)
- [ReadyNAS](ReadyNAS.md)
- [Synology](Synology.md)
- [QNAP](https://github.com/OneCDOnly/sherpa)

---

#### Outdated Packages:

These packages are not yet updated to the new URL, or are simply not maintained anymore. But as long as they are working you should be able to make the switch with manual Git commands.

###### Qnap

- Download the [qpkg](https://www.qnapclub.eu/fr/qpkg/1202)

###### ReadyNas

- https://github.com/SickChill/readynas-sickchill/releases

---

## Git - Update with Git Directly

Go into the SickChill folder and do :

```
git remote set-url origin https://github.com/SickChill/SickChill.git
git fetch origin
git reset --hard origin/master
```

## Switching the Dirty way.

As some installers are outdated or not maintained anymore, switching can be a little frustrating.  
In most cases you can use those old packages in combination with manual Git commands to make the switch.  
However in some cases this is not possible. For those there is a `Dirty` way to switch.

- 1 Run the outdated installer and install sickchill from the old Repo.
- 2 Shutdown SickChill.
- 3 Download the latest SickChill package from the [New Repo](https://github.com/SickChill/SickChill/archive/master.zip).
- 4 Unzip and overwrite the old files on your device.
- 5 Start SickChill again.

That's it.  
However this method is meant as a last resource, and should only be used if all other methods fail.
