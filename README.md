### How to install Docker

```
sudo -i
systemctl disable --now firewalld
yum install wget epel-release git -y
wget -qO- https://get.docker.com/ | sh


systemctl disable --now postfix

usermod -aG docker $(whoami)

systemctl enable --now docker
yum install -y python-pip

pip install docker-compose

yum upgrade python*
git clone https://github.com/fl64/ngfw-testlab

cd ngfw-testlab
docker-conpose up -d
```

### Links:
- Mail server: https://github.com/tomav/docker-mailserver
- Ftp: https://hub.docker.com/r/vimagick/pure-ftpd/
