### Installation
Installation guide can be found on [SynoCommunity](https://synocommunity.com)

After installing it takes **_Several Minutes_** for the gui to become available, if the **package center** says `running` please wait and check again.   
The time it takes to become available depends on your DSM and internet connection, you only have a problem if **package center** says `stopped`.

### Troubleshooting 
Look in the `discussions` and `issues`, both open and closed, sections before raising an **issue**.  
Please include which version, DSM **6** or DSM **7**, along with as much other information you can if you raise an **issue**.

If SickChill doesn't install from **package center** you will need to **ssh** into your DSM and look at the installation log at `/var/logs/packages/sichchill.log` to see what went wrong, include it if you raise an **issue**.

DSM 6 - all files are under `/volumeX/@appstore/sickchill` with data in `/volumeX/@appstore/sickchill/var/data`  
DSM 7 - splits files under two folders `/volumeX/@appstore/sickchill` and data in `/volumeX/@appdata/sickchill/data`  
`X` - the volume number where you installed SickChill.