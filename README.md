# Cent OS7 Bash

### Set hostname
```bash
`hostnamectl set-hostname host.rgdigital.io`
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