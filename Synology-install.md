===

Luckily this is very easy and can be preformed with a few simple steps.

Summery. :

1. Go into SickChill and make a backup.
2. Go to the Synology Package Center and remove the old package SickChill.
3. Then install latest SickChill package from [SynoCommunity](https://synocommunity.com/).
4. Restore your backup, and restart SickChill.

That's it. :+1:

Note: By default the Synocommunity SickChill package uses port 8081, and prior Synocommunity packages used port 8083 or 8899. So if you restore your backup between the two the port will also be restored back. Therefor make sure you open the SickChill page with the correct port. Once running change to 8081 to align with package center link.

###### Need more Synology SickChill info

See the [Synology](https://github.com/SickChill/SickChill/wiki/Synology) set up guide for troubleshooting and other fun DSM information.

---

## Explained with illustrations.

Login to SickChill and go to Backup and Restore in the configuration. Create a backup and store it in a safe location.

![1](https://cloud.githubusercontent.com/assets/7928052/11318354/73fa0d0e-904f-11e5-9432-581a8e795508.png)

Login to Synology's DSM and go into the Package Center and open the SickChill Package. There Select Remove.

![2](https://user-images.githubusercontent.com/10173496/187066254-0ef1324a-f330-49c7-bade-b32504732f7c.png)

On the conformation window pres `YES`.

###### Install SickChill

Now that SickChill is removed we need to (re)install it again. Go to the community overview of Packages, find SickChill and click on `Install`.

# ![1](https://user-images.githubusercontent.com/10173496/187065416-d81b51b8-b49e-4fa1-9564-c67edc9c4eea.png)

Now you will get a wizard/installation screen. Fill-in the username and password or leave blank.  
`Run after installation"` Is as labelled, run immediately after installation complete or allow you to run manually. Manual start is when you have to put your own `config.ini` and `sickchill.db` files in yourself.

# ![2](https://user-images.githubusercontent.com/10173496/187065639-d32e5760-93be-48dd-a710-01e027517b6e.png)

SickChill is now (re)installed.  
Open the GUI and go to Backup/Restore under configuration and restore your backup.

# ![7](https://cloud.githubusercontent.com/assets/7928052/11318357/741a8c14-904f-11e5-94e8-614dc94ede74.png)

Last thing you need to do is a restart of SickChill so the changes take effect.

# ![8](https://cloud.githubusercontent.com/assets/7928052/11318356/740d7dbc-904f-11e5-9e3a-4ebfea556b2e.png)

That's all, you are now running on the new Repository. :)

In some cases you can get a cache warning after restoring the backup. You can ignore those.

```
MAIN :: Restore: Unable to remove the cache/sessions directory: error 2 : No such file or directory
MAIN :: Restore: Unable to remove the cache/indexers directory: error 2 : No such file or directory
```

## Synology SickChill Permissions

Setting permissions for files and folder access in your DSM are key to SC being able to put things in the right place.

There are multiple ways to have SC access your folders. You can do it per [SynoCommunity Permissions](https://github.com/SynoCommunity/spksrc/wiki/Permission-Management) wiki page, or add your own `group` with read/write permissions on folders where you want SC to access files and data then add the `system internal user` `sc-sickchill` via ssh.

The user:group are:  
**DSM6** sc-sickchill:sc-download  
**DSM7** sc-scikchill:synocommunity  

Note:  
The user and group are `system internal user` and not directly assignable in DSM gui and the installation of SC through the `package center` will create them.

Example:  
Create `yourgroup` through control panel `User & Group` then ssh and add `sc-sckchill` to `yourgroup` using  
`sudo synogroup --memberadd yourgroup sc-sickchill`  
Adjusting access to folders via gui using `yourgroup` in `File Station` is now possible.