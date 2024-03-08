- [Where are the LOG files located?](#where-are-the-log-files-located)
- [How do I enable debug logs to get more detailed information in my logs?](#how-do-i-enable-debug-logs-to-get-more-detailed-information-in-my-logs)
- [Does SickChill support NAS devices?](#does-sickchill-support-nas-devices)
- [Windows Shares and Mapped Drives](#windows-shares-and-mapped-drives)
- [(scene exceptions) Releases have a different show name than in SickChill, and are not snatched?](#scene-exceptions-releases-have-a-different-show-name-than-in-sickchill-and-are-not-snatched)
- [Error while searching ..., skipping: 'NoneType' object is not iterable](#error-while-searching--skipping-nonetype-object-is-not-iterable)
- [Reverse Proxy is not working.](#reverse-proxy-is-not-working)
- [I have problems with special characters (é etc.) What can I do?](#i-have-problems-with-special-characters)
- [I have problems updating or my installation got corrupt. What now?](#i-have-problems-updating-or-my-installation-got-corrupt-what-now)
- [I'm currently using the SABtoSickbeard script with SABNZB, however failed downloads don't work.](#im-currently-using-the-sabtosickbeard-script-with-sabnzb-however-failed-downloads-dont-work)
- [Error: Rar Not Supported: No suitable RAR unpacker installed](#error-rar-not-supported-no-suitable-rar-unpacker-installed)
- [I'm getting SSL errors what now?](#im-getting-ssl-errors-what-now)
- [Can I support SickChill? How?](#can-i-support-sickchill-and-how)
- [What does the Episode Status mean and what does it do?](#what-does-the-episode-status-mean-and-what-does-it-do)
- [One of my shows has a missing Network logo.](#one-of-my-shows-has-a-missing-network-logo)
- [What is post processing?](#what-is-post-processing)
- [How do the quality settings for a show work?](#how-do-the-quality-settings-for-a-show-work)
- [Newly aired shows are not downloading and set to skipped/ignored?](#newly-aired-shows-are-not-downloading-and-set-to-skippedignored)
- [How to disable and remove SickChill autostart (_systemctl_) ?](#how-to-disable-and-remove-sickchill-from-autostart)
- [Post-processing shows a negative time](#post-processing-shows-a-negative-time)
- [What is a network time zone warning?](#what-is-a-network-time-zone-warning)
- [Unable to send torrent to synology download station](#unable-to-send-torrent-to-synology-download-station)
- [Timeout when adding a show on Freenas](#timeout-when-adding-a-show-on-freenas)
- [What are Unicode errors?](#what-are-unicode-errors)
- [Why does "Send to trash" option not send the files to the Recycle Bin?](#why-does-the-send-to-trash-option-not-send-the-files-to-the-recycle-bin)

## Where are the LOG files located?

You can find the log files path in _Config->Help & Info_, look for _SC Log Dir_.

_Note: You may need to `ssh` to access them_

## How do I enable debug logs to get more detailed information in my logs?

Go to settings (gearwheels) ---> General ---> Advanced Settings. Enable the setting `Enable debug`. Or set in manually in your config.ini. The line is called `debug = 0` replace the 0 with 1 and save. (Make sure SickChill is not running!)
If you like to upload the log you can use [pastebin] (http://pastebin.org) or an equivalent site.

## Does SickChill support NAS devices?

Yes. There are pre-built NAS versions of SickChill:

- Synology, QNAP, Asustor, Thecus and many others.  
  See the [SickChill installation packages](SickChill-installation-packages) section.

## Windows Shares and Mapped Drives

Make sure Python is allowed through Windows Firewall: [Read How](https://github.com/SickChill/SickChill/issues/3359#issuecomment-289219723)
If the share is not public, you need to edit the SickChill service and change the login to use your user account and your user account MUST have a password set and added to the service login
Mapped drives do not work when using the SickChill Installer, or running SickChill as a service, so you must use UNC paths such as \\\\server\share.
This is because mapped drives are mounted with your user account AFTER SickChill has already started
You can type these paths at the top of the browse dialog popups in SickChill and hit enter to see the contents of the share and add them to SickChill

## (scene exceptions) Releases have a different show name than in SickChill, and are not snatched?

If you encounter torrents/nzbs that use different show names than the one supplied from TheTVDb, you can add a Scene Exception to your show [Go to Show, Edit Show] with the name that the releases are using.
An example is when you have two shows with the same name. To differentiate between the two, uploaders generally will add the premiere year of the show. i.e. _Revolution_, i.e. _Revolution (2012)_
For more information see the [Scene exceptions and numbering](Scene-exceptions-and-numbering) section.

## Error while searching ..., skipping: 'NoneType' object is not iterable

Close SickChill, then delete _cache.db_ in your SickChill directory. This may solve the problem.

If you still have the same issues, search the repository for the error message (without the specific provider name) and if there's an open issue, copy your log (at Debug level). If no such issue exists, open a new one.

## Reverse Proxy is not working.

Make the following changes to your config.ini file:

- _web_host=0.0.0.0_
- _localhost_ip=[your LAN IP]_

## I have problems with special characters.

I have (é etc.) What can I do? It's always a good idea to make sure you're using UTF-8 locale to avoid Unicode decoding issues so please perform the following commands if you're using a Unix operating system.

Add the following lines of code to your ~/.bashrc and ~/.profile files:

```
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
export LANGUAGE=en_US.UTF-8
```

Then run `source ~/.bashrc` in a terminal window.

## I have problems updating or my installation got corrupt. What now?

You can reinstall SickChill through pip, see [pip]().

## I'm currently using the SABtoSickbeard script with SABNZB, however, failed downloads don't work.

Switch to the [NZBtoMedia](NZBtoMedia) scripts. The package contains a script called NZBtoSickbeard. This will provide full and automatic failed download handling. Installation is almost identical to the SABtoSickbeard script.

## Error: Rar Not Supported: No suitable RAR unpacker installed

SickChill has the ability to unpack RAR-archived releases but requires the external `unrar` command on Linux, Mac, FreeBSD, and other Unix OS. In Windows, it uses unrar.dll(x86) or unrar64.dll(x86_64) which are included in SickChill.

If you get this error, you need to make sure unrar is installed and available into PATH.

To install `unrar`:

- Fedora:
  - `yum install -y unrar` Need [RPMFusion repo](http://rpmfusion.org/) installed.
- Ubuntu, Mint, Debian(non-free repo):
  - `apt-get install unrar`
- openSUSE:
  - `zypper install unrar`
- Arch:
  - `pacman -S unrar`
- Mac (brew):
  - `brew install unrar`
- Mac (ports):
  - `port install unrar`

## I'm getting SSL errors what now?

An SSL error looks generally something like this: `_ssl.c:499: error:14077438:SSL routines:SSL23_GET_SERVER_HELLO:tlsv1 alert internal error`  
They are mainly the cause of not having Python installed correctly. Python needs to have the pyOpenSSL & cryptography modules installed to handle HTTPS connections. Note, [QNAP](SickChill-installation-packages#Qnap) users need to have a recent SickChill package installed.

## Can I support SickChill and How?

Yes, absolutely! We are always looking for help. If you are familiar with Python, HTML, Java or other programming languages, please give a shout. Also, if you have experience moderating and want to help users by solving/answering their basic questions regarding SickChill, feel free to help on the SickChill [Discord](https://discord.com/channels/502612977271439372/1048317980343283733). Last, there is the option to [Donate](Donations). That helps us pay for the upkeep/maintaining cost of the SickChill project.

## What does the Episode Status mean and what does it do?

The Episode Status shows (like the name implies) the status of an episode. So is it downloaded and in what quality? Or is it still Wanted? Or skipped? For an extended explanation see the
[Episode Status](Episode-Status) section.

## One of my shows has a missing Network logo.

SickChill uses a network logo to indicate the network on which the show aired. However, with countless networks worldwide it's impossible to keep track/add every logo. If you come across a missing logo please report it (or, when you are able, submit it). For more information see the [Network logos](Network-logos) section.

## What is post processing?

After an episode is downloaded you can automatically modify/change/work on the file. Post processing is the name for this process. It can include a message from your download client (Sabnzb) to SickChill that the file was downloaded, to renaming the episode, or any other form of modifying/testing. Out of the box SickChill contains many options you can use, but if you want even more options then check out the [NZBToMedia](https://github.com/clinton-hall/nzbToMedia) scripts. Also see the [Post-Processing](Post-Processing) section.

## How do the quality settings for a show work?

One of the most important things in SickChill are the Quality Settings. The Quality Settings allow you to instruct SickChill what the quality should be and if it should be snatched, or left alone. For a more detailed explanation see the [Quality Settings](Quality-Settings) section.

## Newly aired shows are not downloading and set to skipped/ignored?

This is due to a [fix](https://github.com/SickChill/SickChill/pull/2078) for a very old bug in SickChill recently. (July 2015)

Previously, when you added a show you had the option for **Default Episode Status** to set the status for episodes that had aired in the past, and all new episodes were automatically set to wanted regardless of your setting, which could be seen from the show page. Now, we have 2 settings when adding a show, Default Episode Status for past episodes, and a Default Episode Status for future episodes. If your shows were added before this change, then your Default Episode Status for future episodes is still set to whatever you added the show with.

**Solution**
Edit each show (or mass update) and correct the Default Episode Status to WANTED (You can also change from wanted to another on shows where you don't want new episodes to be downloaded automatically)

## How to disable and remove SickChill from autostart?

This step could be useful **if you plan to remove/reinstall SickChill** and you would like to _"start fresh"_.

(also, this could be the case if you are migrating to SickChill from other Sick iterations)

```

systemctl stop sickchill
chkconfig sickchill off
systemctl daemon-reload
systemctl reset-failed

```

## Post Processing shows a negative time

In rare cases, the Post Processing stops working and will show a negative time in the
[server status overview](images/serverstatusoverview.png). The cause is a single/bad/corrupt file where PP hangs on, and therefore can't be processed/finished. Your log should be able to tell you which file, then you simply need to remove it.

## What is a network time zone warning?

SickChill uses a file called [network_timezones.txt](https://github.com/SickChill/sickchill.github.io/blob/master/sb_network_timezones/network_timezones.txt) to check the timezone of a tv channel.
This allows SickChill to calculate the exact time that a show airs in your OWN timezone. When it's 12:00 in Europe it's 04:00-06:00 in the US etc.
By knowing this SickChill can start searching on a more precise time. This might help to download an episode faster. (depending on the timezone where you are located.) If there isn't a tv timezone known to SickChill it will start searching by date, so at 0:00 midnight local time.

A network time zone warning will look like this:

`Thread-64 :: Network was not found in the network time zones: Sky Atlantic (IT)`

When you come across such a warning you can add the tv channel and time zone to the [network_timezones.txt](https://github.com/SickChill/sickchill.github.io/blob/master/sb_network_timezones/network_timezones.txt) here.

## Unable to send torrent to Synology Download station.

SickChill supports Synology's Download Station (DLS), but some users can run into problems setting it up correctly.  
One of those is: `WARNING SEARCHQUEUE-BACKLOG-281620 :: [9149089] DownloadStation: Unable to send Torrent `

There are a few things you should check if this happens.  
First, check if the connection test works in the search settings. If that does work then the authentication with DSM is Ok. Then check the following :

- If it's a new DSM account you need to log into DLS with that account first and set a default download folder.
- Does it work with an administrator account.?
- If it's a custom-created folder then set share (folder) permissions in to username sc-sickchill & sc-download (DSM6) or synocommunity (DSM7) as group. [Syno Permissions](Synology-install#Synology-SickChill-Permissions)
- If the path is left blank it will auto-populate, or enter the path but remove `/volume1/` from the path in the settings.

When all else fails then you could also use the black-hole method as a workaround. SickChill will store the nzb/torrent in a folder of your choosing.
Then simply set DS to monitor that folder for nzbs and torrents. As soon as one is found the download will start.

## Timeout when adding a show on Freenas

If you get a timeout when you try to search/add a new show then check your network settings. For FreeNAS you can fix this by going to Network > Interfaces > Select your primary network source > Edit > Uncheck "Autoconfigure IPv6".
Then go to Jails > Select Jail with SickChill > Edit Jail > Advanced Mode > Uncheck "IPv6 Autoconfigure"
Make sure to reboot after you save that.

This could also apply to other devices, so when this timeout happens make sure you check your ipv6 and DNS settings.

## What are Unicode errors?

Those can happen when there are special characters in the show's name, file name, folder name or the search results.
This is mainly a problem on Windows systems and especially with Anime. There are generally more special characters used in Anime.
Sadly not much can be done. But a few things you can try are:

- Rename files and folders to not contain any special characters.
- Add a scene exception (an alternative name for a show) hopefully this will allow you to snatch the episode.

On Linux those Unicode errors generally only happen when you haven't set your locale correctly. Make sure it's UTF-8.

## Why does the "Send to trash" option not send the files to the Recycle Bin?

**(This applies to using NSSM and/or Windows Service _only_)**

[Please attempt this fix.](https://github.com/SickChill/SickChill/issues/3204)
