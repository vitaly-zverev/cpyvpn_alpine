# cpyvpn_alpine

DockerHub: https://hub.docker.com/r/vzverev/cpyvpn_alpine

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/vitaly-zverev/cpyvpn_alpine/HEAD?labpath=TryMeInBinder.ipynb)

```
docker run --rm -ti  \
 --cap-add=NET_ADMIN  \
 --device=/dev/net/tun \
 --name=cpyvpn_alpine \
 --dns=8.8.8.8 \
 --dns=8.8.4.4 \
 --privileged=true \
vzverev/cpyvpn_alpine \
cp_client -m l -u ivanov.i -i tun0 -s /root/vpn/vpnc-scripts/vpnc-script  vpn.example.ru

or 

git clone https://github.com/vitaly-zverev/cpyvpn_alpine && cd cpyvpn_alpine

docker build --force-rm -t cpyvpn_alpine Docker

docker run --rm -ti  \
 --cap-add=NET_ADMIN  \
 --device=/dev/net/tun \
 --name=cpyvpn_alpine \
 --dns=8.8.8.8 \
 --dns=8.8.4.4 \
 --privileged=true \
cpyvpn_alpine \
cp_client -m l -u ivanov.i -i tun0 -s /root/vpn/vpnc-scripts/vpnc-script  vpn.example.ru


```

```
GW url(host) is: vpn.example.ru
Checking SSL mode.
SSL mode is: strict.
Please provide user name and password to authenticate
Password:
Standard login
....
Exception: Authentication error: Access denied - wrong user name or password  (code=101)
```

PS

Recipe also applied for:
https://shell.cloud.google.com/?show=ide%2Cterminal


 docker scan  vzverev/cpyvpn_alpine
Docker Scan relies upon access to Snyk, a third party provider, do you consent to proceed using Snyk? (y/N)
y

Testing vzverev/cpyvpn_alpine...

Package manager:   apk
Project name:      docker-image|vzverev/cpyvpn_alpine
Docker image:      vzverev/cpyvpn_alpine
Platform:          linux/amd64
Base image:        python:3.11.2-alpine3.17

✔ Tested 92 dependencies for known vulnerabilities, no vulnerable paths found.

According to our scan, you are currently using the most secure version of the selected base image

