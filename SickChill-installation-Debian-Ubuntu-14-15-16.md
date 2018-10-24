## Ubuntu 14.x 15.x 16.x
The following instructions are for installing SickChill on Ubuntu 14.x 15.x 16.x
 
The installation is applicable to the upcoming 16.04 LTS as it is the same systemd setup as 15.x. The provided script can distinguish the difference between systemd/init/upstart for you. 
 
The installation assumes that you're not using the root user to install/run sickchill - the entries for **user:group** throughout the document will be set as sickchill:sickchill and you will have to modify if if you want it to match your user configuration.
 
If you trust us and would like us to just do it for you just paste this:

	curl https://raw.githubusercontent.com/SickChill/SickChill/master/contrib/debian-ubuntu-install.sh | sudo bash
	
Otherwise:
 
1. Update repositories and install SickChill dependencies
    This will give you unrar-free (guess), and git to pull the repo
 
   ```bash
   sudo apt-get update && sudo apt-get install unrar-free git-core openssl libssl-dev python2.7
   ```
 
2. Create sickchill user and group
    This makes sure that sickchill is isolated and is best practice for security
   
    ```bash
    sudo addgroup --system sickchill
    sudo adduser --disabled-password --system --home /var/lib/sickchill --gecos "SickChill" --ingroup sickchill sickchill
    ```
   
3. Clone SickChill git repo
 
    ```bash
    sudo mkdir /opt/sickchill && sudo chown sickchill:sickchill /opt/sickchill
    sudo -u sickchill git clone https://github.com/SickChill/SickChill.git /opt/sickchill
    ```

For Init Systems
	
4. Copy init.d service
 
    ```bash
    sudo cp -v /opt/sickchill/runscripts/init.ubuntu /etc/init.d/sickchill
    ```
 
5. Make sure your new service has correct permissions
 
    ```bash
    sudo chown root:root /etc/init.d/sickchill
    sudo chmod 644 /etc/init.d/sickchill
    ```
 
6. Update and start your new service
   
    ```bash
    sudo update-rc.d sickchill defaults
	sudo service sickchill start
    ```
	
For Upstart Systems

4. Copy init.d service
 
    ```bash
    sudo cp -v /opt/sickchill/runscripts/init.upstart /etc/init/sickchill.conf
    ```

5. Make sure your new service has correct permissions
 
    ```bash
    sudo chown root:root /etc/init/sickchill.conf
    sudo chmod 644 /etc/init/sickchill.conf
    ```

6. Update and start your new service
   
    ```bash
    sudo service sickchill start
    ```

For Systemd Systems

4. Copy systemd service
 
    ```bash
    sudo cp -v /opt/sickchill/runscripts/init.systemd /etc/systemd/system/sickchill.service
    ```
 
5. Make sure your new service has correct permissions
 
    ```bash
    sudo chown root:root /etc/systemd/system/sickchill.service
    sudo chmod 644 /etc/systemd/system/sickchill.service
    ```
 
6. Enable, start, and then check the status of your new service
   
    ```bash
    sudo systemctl enable sickchill
    sudo systemctl start sickchill
    sudo systemctl status sickchill
    ```

All done, verify that SickChill is accessible at: http://localhost:8081
