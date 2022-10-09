## CENTOS 6

The following instructions are for installing SickChill on CentOS 6.

The installation should also be applicable to RHEL 6 and Fedora (12, 13, or 14) with minimal changes.

The installation assumes that you're not using the root user to install/run sickchill - the entries for **user:group** throughout the document will have to be modified to match your user configuration.

1. Install rpmFusion non-free repository
   The repository is needed for unrar installation

   ```bash
   sudo rpm -ivh http://download1.rpmfusion.org/nonfree/el/updates/6/i386/rpmfusion-nonfree-release-6-1.noarch.rpm
   ```

2. Install prerequisites

   ```bash
    sudo yum install python-cheetah unrar wget git
   ```

3. Clone sickchill git repo

   ```bash
   sudo git clone https://github.com/SickChill/SickChill.git /usr/share/sickchill
   ```

4. Set correct ownership

   ```bash
   chown -R user:group /usr/share/sickchill
   ```

5. Copy init file to system init

   ```bash
   sudo cp /usr/share/sickchill/init.fedora /etc/init.d/sickchill
   ```

6. Make init file executable

   ```bash
   sudo chmod +x /etc/init.d/sickchill
   ```

7. Modify init file

   ```bash
   sudo sed 's|/etc/sysconfig/sickbeard|/etc/sysconfig/sickchill|' -i /etc/init.d/sickchill
   ```

8. Create configuration file /etc/sysconfig/sickchill with the following content

   ```bash
   # SickChill service configuration

   #run SickChill as
   SR_USER=media
   SR_HOME=/usr/share/sickchill
   SR_DATA=/usr/share/sickchill
   SR_PIDFILE=/usr/share/sickchill/sickchill.pid

   #gui address, eg: \${protocol}://\${host}:\${port}/home/
   protocol=http
   host='<<< hostname or IP >>>' #example host=mymachine
   port='<<<Desired Port>>>'     #example port=8081

   #leave blank if no username/password is required to access the gui
   username=
   password=

   #use nice, ionice, taskset to start SickChill
   nicecmd=
   #  example: nicecmd="nice -n 19 ionice -c3"
   ```

9. Add the sickchill service to system services

   ```bash
   sudo chkconfig --add sickchill
   ```

10. Configure sickchill service to start on system startup

    ```bash
    sudo chkconfig sickchill on
    ```

11. Start sickchill service

    ```bash
    sudo service sickchill start
    ```

All done, verify that SickChill is accessible at gui address, eg: http://mymachine:8080/sickchill

Celebrate with some impromptu dancing!!
