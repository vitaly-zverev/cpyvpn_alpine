# cpyvpn_alpine

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/vitaly-zverev/cpyvpn_alpine/HEAD?labpath=TryMeInBinder.ipynb)

```
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
