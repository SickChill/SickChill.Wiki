## Installation

Installation guide can be found on [SynoCommunity](https://synocommunity.com)

After installing it takes **_Several Minutes_** for the gui to become available, if the **package center** says `running` please wait and check again.  
The time it takes to become available depends on your DSM and internet connection, you only have a problem if **package center** says `stopped`.

## Troubleshooting

Look in the `discussions` and `issues`, both open and closed before raising an **issue**.  
Please include which version, DSM **6** or DSM **7**, along with as much other information you can if you raise an **issue**.

If SickChill doesn't install from **package center** you will need to **ssh** into your DSM and look at the installation log at `/var/logs/packages/sichchill.log` to see what went wrong, include it if you raise an **issue**. This is a different log file to the **SC** log under `data/logs` and is the same info you'd see if you run from `ssh` terminal.

### _Where are the **SC** files?_

SC: `/volume1/@appstore/sickchill/env/lib/python3.10/site-packages/sickchill` ~~`/volume1/@appstore/sickchill`~~  
Env: `/volume1/@appstore/sickchill/env/`  
Python3: `/volume1/@appstore/sickchill/env/bin/python3`  
Python packages: `/volume1/@appstore/sickchill/env/lib/python3.10/site-packages/` [Py 3.10]  
DSM6 data: `/volume1/@appstore/sickchill/var/data/`  
DSM7 data: `/volume1/@appdata/sickchill/data/`  
`volume1` - depends on the volume you installed SickChill.

### How to Run **SC** form SSH terminal

First open ssh terminal and switch to `sc-sichchill` user by

    sudo -u sc-sickchill /bin/bash

Then depending on your DSM version use the appropriate string to Run **SC**.  
DSM6:

    /volume1/@appstore/sickchill/env/bin/python3 /volume1/@appstore/sickchill/share/SickChill/SickChill.py --config /volume1/@appstore/sickchill/var/data/config.ini --datadir /volume1/@appstore/sickchill/var/data

DSM7:

    /volume1/@appstore/sickchill/env/bin/python3 /volume1/@appstore/sickchill/share/SickChill/SickChill.py --config /volume1/@appdata/sickchill/data/config.ini --datadir /volume1/@appdata/sickchill/data

### How to install / update packages

1.  `sudo -u sc-sickchill /bin/bash`
2.  `cd /volume1/@appstore/sickchill/env/lib/python3.10/site-packages/`
3.  `/volume1/@appstore/sickchill/env/bin/python3 -m pip install "XXX"`  
    ^XXX^ options and packages.
