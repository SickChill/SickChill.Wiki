## Introduction

---

For many novice users installing SickChill on a Windows machine can be confusing.
Therefore we have created a Windows installer to simplify the process. This installer will download all the necessary files and automatically install them for you.
It also will take care of creating a service, so that SickChill will automatically start with Windows.
Both x32 and x64-bit installations are supported and automatically recognized.

For more detailed information checkout https://github.com/SickChill/SickChillInstaller#sickchillinstaller

## Network drive mappings

The installer uses a service (account) to run SickChill automatically on startup. This is a different account than your Windows user account which you use to login to Windows. Meaning that any network drive mappings do not exist for that (service) account and need to be created.
Or edit the service to run with another [account](https://technet.microsoft.com/en-us/library/cc755249.aspx) that has the network drive mappings setup.
You can manually change the account from the command prompt (administrative rights) with the below commands. :

```
sc config "SickChill" obj= "username" password= "password"
sc restart SickChill
```

If you are unable to get those setup correctly, you can always disable the service and start SickChill manually. SickChill will then run as the user that is logged in to Windows. Alternatively, you can also install SickChill [manually](https://github.com/SickChill/SickChill/wiki/SickChill-Windows-Installer#manual-installation-guides-for-windows)

---

## Installing SickChill on Windows

Head over to the [SickChill Package Installer](https://github.com/SickChill/SickChillInstaller/releases) and download the latest release.  
(Special thanks to VinceVal for compiling this installer.)

Browse to the folder/location where you have placed the installer file and execute/run it.  
(You might get a warning from `users account control` that the program is `Unknown`. Just ignore the warning, and click on `OK`.)

--
![1](https://user-images.githubusercontent.com/11801385/273109083-6e0a34e3-14b0-413a-b0ed-77a85af0e31f.PNG)

You will be greeted by the welcome screen.
Click on `Next >` to proceed with the installation.

--

![2](https://user-images.githubusercontent.com/11801385/273109115-3d5e8c6c-2633-4d1d-80b2-ff0ab055f9b0.PNG)

The next window lets you select the destination folder where you want SickChill to be installed. the default is `C:\SickChill`  
Use `Browse...` if you would like to change that location. Or enter the destination manually in the text field.  
Click on `Next >` to proceed with the installation.

--

![3](https://user-images.githubusercontent.com/11801385/273109122-92b0ebf3-63aa-4e36-bd74-6d01f57ae574.PNG)

The next window will ask if you would like a shortcut to be created in your start menu.  
If not than check the check-box `Don't create a Start Menu folder`  
Click on `Next >` to proceed with the installation.

--

![4](https://user-images.githubusercontent.com/11801385/273109131-cb595a4f-0831-4d9f-9bd6-77d20a577750.PNG)

The next window will let you set the port on which SickChill will run. The default is `8081` and it's advised not to change this, unless you have a good reason for it.  
Click on `Next >` to proceed with the installation.

--

![6](https://user-images.githubusercontent.com/11801385/273109144-8d0f2c47-aeb0-4ac2-aeca-d6a03ae33a93.PNG)

The next window will ask if you would like to create a shortcut for SickChill on your desktop.  
For ease, it's recommended to create a shortcut on the desktop. But you can also decide to save the URL as a bookmark/favorite in your browser later.  
Click on `Next >` to proceed with the installation.

--

![7](https://user-images.githubusercontent.com/11801385/273109157-6f960494-e97f-4172-979f-1e4cb3bdaacb.PNG)

The next window shows you an overview of the settings you have selected and the dependencies that will be installed together with SickChill.  
(Those dependencies are needed to run and update SickChill on your Windows machine.)  
Click on `Install` to proceed with the installation.

--

![8](https://user-images.githubusercontent.com/11801385/273109166-806fb2f0-e484-4750-9b19-b109c446b55b.PNG)

The next window will start downloading the necessary files that are going to be used to install SickChill.

--

![9](https://user-images.githubusercontent.com/11801385/273109180-4a8b9447-85de-4795-be56-25825cb2974e.PNG)

The next window will show you the installation of the downloaded files, this can take a moment depending on your machine.

--

![10](https://user-images.githubusercontent.com/11801385/273109197-79a41fc3-d759-4787-8569-783598f6b889.PNG)

When the installation is complete you will get the `Finish` screen. Simply click on `Finish` to complete the installation.  
Congratulations, you have successfully installed SickChill.! :+1:

--

![11](https://user-images.githubusercontent.com/11801385/273109209-d3c253e8-2534-4a78-a261-88f8d6bfb107.PNG)

Now you can access SickChill by opening your favorite browser and go to http://localhost:8081 to open SickChill's Web-interface.

--

---

## Manual installation guides for Windows

In case you prefer to do the installation manually, then you can have a look at the below guides. Note that Cheetah isn't necessary anymore, so you don't have to install it.

`Official Windows installer:`  
https://github.com/SickChill/SickChillInstaller
