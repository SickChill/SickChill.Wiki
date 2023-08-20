## Ubuntu 14.x to 22.x

The following instructions are for installing SickChill on Ubuntu 14.x 15.x 16.x 18.x 20.x 22.x

The installation is applicable to up to and including Ubuntu 22.04 LTS, the provided script can distinguish the difference between systemd/init/upstart for you.

The installation assumes that you're not using the root user to install/run sickchill - the entries for **user:group** throughout the document will be set as sickchill:sickchill and you will have to modify if you want it to match your user configuration.  

If you trust us and would like us to just do it for you just paste this:

```shell
curl https://raw.githubusercontent.com/SickChill/SickChill/master/contrib/debian-ubuntu-install.sh | sudo bash
```

Otherwise:

1. Update repositories and install SickChill dependencies.  
   This will give you unrar-free (guess) and git to pull the repo, as well as any other requirements for building the package. The name of the `python3-venv` package you need to install may be different to what is listed here - in this case you will be prompted with the updated version at a later step.  

  ```shell
sudo apt-get update && sudo apt-get install unrar-free git-core openssl libssl-dev python3 python3-pip python3.10-venv
  ```

2. Create sickchill user and group, and switch to `sickchill`.  
    This makes sure that sickchill is isolated and is best practice for security  
  ```shell
sudo addgroup --system sickchill
sudo adduser --disabled-password --system --home /var/lib/sickchill --gecos "SickChill" --ingroup sickchill sickchill  
sudo su sickchill
  ```
3. Set up a Python virtual environment  
  ```shell
python3 -m venv /opt/sickchill
  ```
4. Install the required dependencies with pip
  ```shell
/opt/sickchill/bin/pip install -U pip setuptools wheel
  ```
5. Install SickChill
  ```shell
/opt/sickchill/bin/pip install -U sickchill
  ```
For Init Systems
6. Copy init.d service
```shell
sudo cp -v /opt/sickchill/runscripts/init.ubuntu /etc/init.d/sickchill
```
7. Make sure your new service has correct permissions
  ```shell
sudo chown root:root /etc/init.d/sickchillsudo chmod 644 /etc/init.d/sickchill
  ```
8. Update and start your new service
  ```shell
sudo update-rc.d sickchill defaultssudo service sickchill start
  ```
For Upstart Systems
6. Copy init.d service
  ```shell
sudo cp -v /opt/sickchill/runscripts/init.upstart /etc/init/sickchill.conf
  ```
7. Make sure your new service has correct permissions
  ```shell
sudo chown root:root /etc/init/sickchill.confsudo chmod 644 /etc/init/sickchill.conf
  ```
8. Update and start your new service
  ```shell
sudo service sickchill start
  ```
For Systemd Systems
6. Copy systemd service
  ```shell
sudo cp -v /opt/sickchill/runscripts/init.systemd /etc/systemd/system/sickchill.service
  ```
7. Make sure your new service has correct permissions
  ```shell
sudo chown root:root /etc/systemd/system/sickchill.servicesudo chmod 644 /etc/systemd/system/sickchill.service
  ```
8. Enable, start, and then check the status of your new service
  ```shell
sudo systemctl enable sickchillsudo systemctl start sickchillsudo systemctl status sickchill
  ```
All done, verify that SickChill is accessible at: [http://localhost:8081/](http://localhost:8081)