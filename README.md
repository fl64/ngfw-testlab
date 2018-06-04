### How to install and run

#### Install
```shell
sudo -i
systemctl disable --now firewalld
yum install wget epel-release git -y
wget -qO- https://get.docker.com/ | sh


systemctl disable --now postfix

systemctl enable --now docker
yum install -y python-pip

pip install docker-compose

yum upgrade python*
git clone https://github.com/fl64/ngfw-testlab

exit
#---
sudo usermod -aG docker $(whoami)
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
