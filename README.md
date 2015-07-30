# Keyboard Map file to set the XRDP server into Spanish

Download the **[km-040a.ini](km-040a.ini)** file into the ```/etc/xrdp/``` folder and then, replace the owner and the group of the file through the next command:

```sh
pi@raspberrypi /etc/xrdp $ sudo chown xrdp.xrdp hm-040a.ini
```

After that, you have to restart the XRDP service with this command:

```sh
pi@raspberrypi /etc/xrdp $ sudo service xrdp restart
```

Once the GUI has been closed, you will have to rerun the ```rdesktop``` command this way, from the host where you want to get the remote desktop:

```sh
rdesktop [-u <username> -p <password>] -k <keyboard-map> <Raspberry Pi IP address>
```

for example...

```sh
rdesktop -u pi -p raspberry -k es 192.168.1.106
```

The shown options are next:

* ```-u <username>``` - Username for authentication on the server.
* ```-p <password>``` - The password to authenticate with. Note that this may have no effect if "Always prompt for password" is enabled on the server. WARNING: if you specify a password on the command line it may be visible to other users when they use tools like ps.
* ```-k <keyboard-map>``` - Keyboard layout to emulate. This requires a corresponding keymap file to be installed. The standard keymaps provided with rdesktop follow the RFC1766 naming scheme: a language code followed by a country code if necessary - e.g. en-us, en-gb, de, fr, sv, etc.

    On this case, due to we are configuring the Spanish keyboard, we have to set **es** as keyboard-map.

If you want to get more information about the ```rdesktop``` options, you can surf to [this link](http://linux.die.net/man/1/rdesktop).
