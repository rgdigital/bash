# Cent OS7 Bash

### Set hostname
**https://forum.linode.com/viewtopic.php?t=14952&p=73921**
```bash
hostnamectl set-hostname host.rgdigital.io
```

### Disable Network manager
**https://documentation.cpanel.net/display/CKB/How+to+Disable+Network+Manager**
```bash
systemctl stop NetworkManager.service
systemctl disable NetworkManager.service
```

### Setup cPanel on fresh CentOS7 server
**https://github.com/tripflex/cpsetup**
```bash
wget https://github.com/tripflex/cpsetup/raw/master/cpsetup
chmod +x cpsetup
./cpsetup
```

# Ubuntu 16.04 LTE Bash

### Setting your FQDM

- Find your current FQDN by checking your hosts file with `sudo nano /etc/hosts`
- The first part can be whatever word you like
- The second part is the domain name
- EG, a FQDN could be `earth.rgdigital.io`

Set your host name with -

`hostname earth.rgdigital.io`

Edit httpd.conf -
`ServerName earth.rgdigital.io`

Finally, go to the linode manager > Network tab, and set your reverse dns to `earth.rgdigital.io`.

### Checking Apache2 config errors

If you try to restart apache with -
`sudo service apache2 restart`

and you get an error, you can run -
`sudo apache2ctl configtest`

This will print out errors in your apache config upon starting the server

### Take ownership of current directory recursively with currently logged-in user
`sudo chown -R $(id -u):$(id -g) ./`

### Take ownership of local git repo if you get Error

Error - `insufficient permission for adding an object to repository database .git/objects`

`sudo chown -R $USER:$USER "$(git rev-parse --show-toplevel)/.git"`

