### CentOS 74

#### Set dynamic IP
nmcli con mod ens192 connection.autoconnect true ipv4.method manual ipv4.addresses 192.168.127.199/22 ipv4.gateway 192.168.124.4 ipv4.dns 8.8.8.8
systemctl restart network

#### Set dynamic IP
nmcli con mod ens192 connection.autoconnect true ipv4.method auto ipv4.addresses "" ipv4.gateway "" ipv4.dns ""

#### Start connection
nmcli con up ens192

#### Stop connection
nmcli con down ens192


### How to install and run

#### Install
```shell
sudo -i
systemctl disable --now {firewalld,postfix}
yum install wget epel-release git -y && yum install python-pip -y
wget -qO- https://get.docker.com/ | sh
systemctl enable --now docker
yum upgrade python* -y
pip install docker-compose



exit
#---
git clone https://github.com/fl64/ngfw-testlab
sudo usermod -aG docker $(whoami) && newgrp docker # Добавить текущего пользователя в группу docker для выполнения команд по управлению контейнерами без sudo
```
#### Run
```shell
cd ngfw-testlab
docker-compose up -d
```
#### Stop
```shell
docker-compose down
```



### Links:
- Mail server: https://github.com/tomav/docker-mailserver
- Ftp: https://hub.docker.com/r/vimagick/pure-ftpd/
