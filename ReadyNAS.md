* **Backup SickChill settings**

* Install Python 3.6.9
```bash
apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev libgdbm-dev libnss3-dev libssl-dev openssl
cd /root
wget http://www.python.org/ftp/python/3.6.9/Python-3.6.9.tgz
tar zxf Python-3.6.9.tgz
cd Python-3.6.9
./configure --enable-loadable-sqlite-extensions --enable-optimizations
make
make altinstall
```
Update SickChill
Test new SickChill
```bash
/usr/local/bin/python3.6 /<YourSickChillLocation>/SickChill.py
```
Update your sickchill.service to use python3.6