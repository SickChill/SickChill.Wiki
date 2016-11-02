* [Where are the LOG files located?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#where-are-the-log-files-located)
* [How do i enable debug logs to get more detailed information in my logs?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#how-do-i-enable-debug-logs-to-get-more-detailed-information-in-my-logs)
* [Does SickRage support NAS devices?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#does-sickrage-support-nas-devices)
* [(scene exceptions) Releases have a different show name than in SickRage, and are not snatched?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#scene-exceptions-releases-have-a-different-show-name-than-in-sickrage-and-are-not-snatched)
* [Error while searching ..., skipping: 'NoneType' object is not iterable](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#error-while-searching--skipping-nonetype-object-is-not-iterable)
* [Reverse Proxy is not working.](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#reverse-proxy-is-not-working)
* [I have problems with special characters (é etc.) What can i do?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#i-have-problems-with-special-characters-%C3%A9-etc-what-can-i-do)
* [I have problems updating or my installation got corrupt. What now?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#i-have-problems-updating-or-my-installation-got-corrupt-what-now)
* [I'm currently using the SABtoSickbeard script with SABNZB, however failed downloads dont work.](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#im-currently-using-the-sabtosickbeard-script-with-sabnzb-however-failed-downloads-dont-work)
* [Error: Rar Not Supported: No suitable RAR unpacker installed](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#error-rar-not-supported-no-suitable-rar-unpacker-installed)
* [I'm getting SSL errors what now?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#im-getting-ssl-errors-what-now)
* [Can i support SickRage? How?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#can-i-support-sickrage-and-how)
* [What does the Episode Status mean and what does it do?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#what-does-the-episode-status-mean-and-what-does-it-do)
* [One of my shows has a missing Network logo.](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#one-of-my-shows-has-a-missing-network-logo)
* [What is post processing?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#what-is-post-processing)
* [How do the quality settings for a show work?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#how-do-the-quality-settings-for-a-show-work)
* [Newly aired shows are not downloading and set to skipped/ignored?](https://github.com/SickRage/SickRage/wiki/FAQ%27s-and-Fixes#newly-aired-shows-are-not-downloading-and-set-to-skippedignored) 
* [Update problems? Try this](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#update-problems-try-this)
* [Enable Debug For Logs](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#enable-debug-for-logs)
* [How to switch to the new Repo?](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#how-to-switch-to-the-new-repo)
* [Post-processing shows a negative time](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#post-processing-shows-a-negative-time)
* [What is a network time zone warning?](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#what-is-a-network-time-zone-warning)  
* [Unable to sent torrent to synology download station](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#unable-to-sent-torrent-to-synology-download-station)  
* [Timeout when adding a show on Freenas](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#timeout-when-adding-a-show-on-freenas)
* [What are Unicode errors?](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#what-are-unicode-errors)
* [How to switch to a older sickrage version?](https://github.com/SickRage/SickRage/wiki/FAQ's-and-Fixes#How-to-switch-to-a-older-sickrage-version?)

##Where are the LOG files located?
You can find the log files path in _Config->Help & Info_, look for *SR Log Dir*.

*Note: Synology users can use WinSCP to gain access/browse to the root where the Sickrage log is located: `/volume1/@appstore/sickrage/var/Logs/sickrage.log`*  

## How do i enable debug logs to get more detailed information in my logs?  
Go to settings (gearwheels) ---> General ---> Advanced Settings. Enable the setting `Enable debug`. Or set in manually in your config.ini. The line is called `debug = 0` replace the 0 with 1 and save. (Make sure SickRage is not running!)
If you like to upload the log you can use [pastebin] (http://pastebin.org) or an equivalent site.  

##Does SickRage support NAS devices?
Yes. There are pre-built NAS versions of SickRage:
* Synology, QNAP, Asustor, Thecus and many others.  
See the [SickRage installation packages](https://github.com/SickRage/SickRage/wiki/Sickrage-installation-packages) section.  


##(scene exceptions) Releases have a different show name than in SickRage, and are not snatched?
If you encounter torrents/nzbs that use different show names than the one supplied from TheTVDb or TVRage, you can add a Scene Exception to your show [Go to Show, Edit Show] with the name that the releases are using. 
An example is when you have two shows with the same name. To differentiate between the two, uploaders generally will add the premiere year of the show. i.e. _Revolution_, i.e. _Revolution (2012)_
For more information see the [Scene exceptions and numbering](https://github.com/SickRage/SickRage/wiki/Scene-exceptions-and-numbering) section.  

##Error while searching ..., skipping: 'NoneType' object is not iterable
Close SickRage, then delete _cache.db_ in your SickRage directory. This may solve the problem. 

If you still have the same issues, search the repository for the error message (without the specific provider name) and if there's an open issue, copy your log (at Debug level). If no such issue exists, open a new one. 

##Reverse Proxy is not working.

Make the following changes to your config.ini file:
* _web_host=0.0.0.0_
* _localhost_ip=[your LAN IP]_


## I have problems with special characters (é etc.) What can i do?  
It's always a good idea to make sure you're using UTF-8 locale to avoid unicode decoding issues so please perform the following commands if you're using a unix operating system.

Add the following lines of code to your ~/.bashrc and ~/.profile files:  

````
export LC_ALL=en_US.UTF-8  
export LANG=en_US.UTF-8  
export LANGUAGE=en_US.UTF-8  
````

Then run `source ~/.bashrc` in a terminal window.
  
## I have problems updating or my installation got corrupt. What now?  
You can enable the `Git Reset` setting under general --> advanced settings.
Or you can do a manual Git reset so that your installation is refreshed.

````
git remote add upstream https://github.com/SickRage/SickRage.git
git fetch upstream
git checkout master
git branch -u upstream/master
git reset --hard upstream/master
git pull
````

## I'm currently using the SABtoSickbeard script with SABNZB, however failed downloads dont work.  
Switch to the [NZBtoMedia](https://github.com/SickRage/SickRage/wiki/NZBtoMedia) scripts. The package contains a script called NZBtoSickbeard. This will provide full and automatic failed download handling. Installation is almost identical as the SABtoSickbeard script.  


##Error: Rar Not Supported: No suitable RAR unpacker installed
SickRage has the ability to unpack RAR-archived releases but require the external `unrar` command on Linux, Mac, FreeBSD and other Unix OS. In Windows, it use unrar.dll(x86) or unrar64.dll(x86_64) which are included in SickRage.

If you get this error, you need to make sure unrar is installed and available into PATH.

To install `unrar`:
* Fedora:
  * `yum install -y unrar` Need [RPMFusion repo](http://rpmfusion.org/) installed.
* Ubuntu, Mint, Debian(non-free repo):
  * `apt-get install unrar`
* openSUSE:
  * `zypper install unrar`
* Arch:
  * `pacman -S unrar`
* Mac (brew):
  * `brew install unrar`
* Mac (ports):
  * `port install unrar`

## I'm getting SSL errors what now?
A SSL error looks generally something like this: `_ssl.c:499: error:14077438:SSL routines:SSL23_GET_SERVER_HELLO:tlsv1 alert internal error`  
They are mainly the cause of not having Python installed correctly. Python needs to have the pyOpenSSL & cryptography modules installed to handle HTTPS connections. For more information see the [SSL Errors](https://github.com/SickRage/SickRage/wiki/SSL-Errors) section. Note, [QNAP](https://github.com/SickRage/SickRage/wiki/Sickrage-installation-packages#qnap) users need to have a recent SickRage package installed.

## Can i support SickRage? How?
Yes, of course you can! We are always looking for help. If you are familiar with Python, HTML, Java or other programming languages, please give a shout. Also, if you have experience moderating and want to help users by solving/answering their basic questions regarding SickRage, feel free to help on the SickRage [Issue Tracker](https://github.com/SickRage/SickRage) and [IRC Channel](https://kiwiirc.com/client/irc.freenode.net/?theme=basic#sickrage-issues). Last there is, of course, the option to [Donate](https://github.com/SickRage/SickRage/wiki/Donations) that helps us pay for the upkeep/maintaining cost of the SickRage project.  

## What does the Episode Status mean and what does it do?
The Episode Status shows (like the name implies) the status of an episode. So is it downloaded and in what quality? Or is it still Wanted? Or skipped? For an extended explanation see the 
[Episode Status](https://github.com/SickRage/SickRage/wiki/Episode-Status) section.  

## One of my shows has a missing Network logo.
SickRage uses a network logo to indicate the network on which the show aired. However with countless networks world wide it's impossible to keep track/add every logo. If you come across a missing logo please report it (or, when you are able, submit it). For more information see the [Network logos](https://github.com/SickRage/SickRage/wiki/Network-logos) section.  

## What is post processing? 
After an episode is downloaded you can automatically modify/change/work on the file. Post processing is the name for this process. It can include a message from your download client (Sabnzb) to SickRage that the file was downloaded, to renaming the episode, or any other form of modifying/testing. Out of the box SickRage contains many options you can use, but if you want even more options then check out the [NZBToMedia](https://github.com/clinton-hall/nzbToMedia) scripts. Also see the [Post-Processing](https://github.com/SickRage/SickRage/wiki/Post-Processing) section.  

## How do the quality settings for a show work?
One of the most important things in SickRage are the Quality Settings. The Quality Settings allow you to instruct SickRage what the quality should be and if it should be snatched, or left alone. For a more detailed explanation see the [Quality Settings](https://github.com/SickRage/SickRage/wiki/Quality-Settings) section.  

##Newly aired shows are not downloading and set to skipped/ignored?  
This is due to a [fix](https://github.com/SickRage/SickRage/pull/2078) for a very old bug in SickRage recently. (July 2015)  

Previously, when you added a show you had the option for __Default Episode Status__ to set the status for episodes that had aired in the past, and all new episodes were automatically set to wanted regardless of your setting, which could be seen from the show page. Now, we have 2 settings when adding a show, Default Episode Status for past episodes, and a Default Episode Status for future episodes. If your shows were added before this change, then your Default Episode Status for future episodes is still set to whatever you added the show with.

__Solution__
Edit each show (or mass update) and correct the Default Episode Status to WANTED (You can also change from wanted to another on shows where you don't want new episodes to be downloaded automatically)

## Update problems? Try this:

Stop SickRage, SSH(Linux)/CMD(Windows) and enter SickRage folder
````
git remote set-url origin https://github.com/SickRage/SickRage.git
git fetch origin
git checkout master
git branch -u origin/master
git reset --hard origin/master
git pull
````
When you get the below error and cant update, then check the line `git_remote = origin` in your config.ini.  
Its probbebly missing the `origin`. If so, shutdown Sickrage and add it. Then restart. 

`git pull -f master returned : fatal: 'master' does not appear to be a git repository`  

## ENABLE DEBUG FOR LOGS  
1. Open SR interface  
2. Menu General Settings > Advanced Settings  
3. Enable 'Enable debug'  

Synology & QNAP users can use [WinSCP](https://winscp.net/eng/download.php) to access/browse SSH to extract the full SickRage log. For example: /volume1/@appstore/sickrage/var/Logs/sickrage.log


## How to switch to the new Repo?

Luckily it's very easy, but it depends a little on what device you are running Sickrage.
The quickest way is to switch with a few simple Git commands, which is explained below: 

First make a backup from within Sickrage, or manually backup `config.ini` & `sickbeard.db`.

Note: You need to run the below commands in your SickRage folder. And make sure you run the commands with the same User as you run Sickrage with, or permission problems may occur.


* First stop the SickRage service

```
git remote set-url origin https://github.com/SickRage/SickRage.git
git fetch origin
git prune && git remote prune origin
git reset --hard origin/master
```

* Start the Sickrage service
* Do another restart of SickRage so all changes can take effect

If you installed Sickrage with an installer than check the [installation packages](https://github.com/SickRage/SickRage/wiki/Sickrage-installation-packages) wiki for a new version. Then simply reinstall with that new  installer, and restore the backup. The above procedure isn't necessary than. But it also works.  
Synology users can find a How-to [here](https://github.com/SickRage/SickRage/wiki/Switching-your-Synology's-Sickrage-to-the-new-repository). And for Windows users making a backup, and reinstalling with the latest [Windows installer](https://github.com/VinceVal/SickRageInstaller/releases/latest) is advised.  
More info on packages/installers you can find [here](https://github.com/SickRage/SickRage/wiki/Sickrage-installation-packages)

Note : As of February 2016 the old repo has bumped the database version (sickbeard.db) from v42 to v44 without any changes. Just to frustrate/discourage users from switching. It still works fine, but you will get a warning during startup that its outdated. If you are annoyed with the warning message and are familiar with SQL than you can run the below commands.:  
`sqlite3 sickbeard.db 'UPDATE db_version SET db_version=42, db_minor_version=1' `  
(Or use any other preferred tool to set the db_version to 42.)  
And off-course you can always build a new database using [Meta-data](https://github.com/SickRage/SickRage/wiki/MetaData)  

## Post Processing shows a negative time

In rare cases the Post Processing stops working and will show a negative time in the 
[server status overview](https://cloud.githubusercontent.com/assets/7232810/12236081/a17e4fec-b82c-11e5-8a37-1d58646e766a.png). The cause is a lone/bad/corrupt file where PP hangs on, and therefor can't be processed/finished. Your log should be able to tell you which file, than you simply need to remove it.  


## What is a network time zone warning?

Sickrage uses a file called [network_timezones.txt](https://github.com/SickRage/sickrage.github.io/blob/master/sb_network_timezones/network_timezones.txt) to check the timezone of a tv channel.
This allows Sickrage to calculate the exact time that a show airs in your OWN timezone. When it's 12:00 in Europe its 04:00-06:00 in the US etc.
By knowing this Sickrage can start searching on a more precise time. This might help downloading an episode quicker. (depending on the timezone where you are located.) If there isn't a tv timezone known to Sickrage it will start searching by date, so at 0:00 midnight local time.

An network time zone warning will look like this: 

`Thread-64 :: Network was not found in the network time zones: Sky Atlantic (IT)`

When you come across such a warning you can add the tv channel and timezone to the [network_timezones.txt](https://github.com/SickRage/sickrage.github.io/blob/master/sb_network_timezones/network_timezones.txt) here.

## Unable to sent torrent to Synology Download station.

Sickrage supports Synology's Download Station, but some users can run into problems setting it up correctly.  
One of those is : `WARNING SEARCHQUEUE-BACKLOG-281620 :: [9149089] DownloadStation: Unable to send Torrent `  

There are a few things you should check if this happens.  
First check it the connection test works in the search settings. If that does work than the authentication with DSM is Ok. Than check the following. :  

* If its a new DSM account then you first need to login with the account to set a default download folder in DownloadStation.
* Does it work with an administrator account.?
* If its a custom created folder than set share (folder) permissions in the sc-media & sc-download user-groups.
* If using DSM 6 than remove `/volume1/` from the [path](https://github.com/SickRage/SickRage/issues/610#issuecomment-181091059 ) in the search settings. 

When all fails than you could also use the black-hole method as a work around. Sickrage will store the nzb/torrent in a folder of your choosing.
Then simply set DS to monitor that folder for nzbs and torrents. As soon as one is found the download will start. 

## Timeout when adding a show on Freenas

If you get a timeout when you try to search/add a new show then check your network settings. For freeNAS you can fix this by going to Network > Interfaces > Select your primary network source > Edit > Uncheck "Autoconfigure IPv6".
Then goto Jails > Select Jail with Sickrage > Edit Jail > Advanced Mode > Uncheck "IPv6 Autoconfigure"
Make sure to reboot after you save that.

This could also apply to other devices, so when this timeout happens make sure you check your ipv6 and DNS settings. 

## What are Unicode errors?

Those can happen when there are special characters in the shows name, file name, folder name or the search results.
This is mainly a problem on Windows systems and especially with Anime. As there are generally more special characters used in Anime.
Sadly not much can be done. But a few things you can try are. :

* Rename files and folders to not contain any special characters.
* Add a scene exception (alternative name for a show) hopefully this will allow you to snatch the episode. 

On Linux those Unicode errors generally only happen when you haven't set your locale correctly. Make sure its UTF-8.


## How to switch to a older sickrage version?

Its possible to switch between different versions of sickrage.
This can be handy for troubleshooting, or if your device has problems with the latest versions.
For this you can use the git checkout command. for example. :

`git checkout v2016.10.20-1`

This will update/downgrade your installation to the v2016.10.20-1 release.
A compleete list of the releases/version can be found [here.](https://github.com/SickRage/SickRage/releases)
(Dont forget to disable the auto update function if you dont want to update.)
Also be aweare that we dont support older/outdated Sickrage versions.