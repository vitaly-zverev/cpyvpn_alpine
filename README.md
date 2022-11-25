# cpyvpn_alpine

```
git clone https://github.com/vitaly-zverev/cpyvpn_alpine && cd cpyvpn_alpine

docker build --force-rm -t cpyvpn_alpine .

docker run --rm -ti  \
 --cap-add=NET_ADMIN  \
 --device=/dev/net/tun \
 --name=cpyvpn_alpine \
 --dns=8.8.8.8 \
 --dns=1.1.1.1 \
 --privileged=true \
cpyvpn_alpine \
cp_client -m l -u ext-i.ivanov -i tun0 -s /root/vpn/vpnc-scripts/vpnc-script  vpn.russianpost.ru


```

'''
GW url(host) is: vpn.russianpost.ru
Checking SSL mode.
SSL mode is: strict.
Please provide user name and password to authenticate
Password:
Standard login
Traceback (most recent call last):
  File "/usr/local/bin/cp_client", line 33, in <module>
    sys.exit(load_entry_point('cpyvpn==0.0.0', 'console_scripts', 'cp_client')())
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/cpyvpn-0.0.0-py3.11.egg/cpyvpn/client.py", line 432, in main
  File "/usr/local/lib/python3.11/site-packages/cpyvpn-0.0.0-py3.11.egg/cpyvpn/client.py", line 234, in vpn_main
  File "/usr/local/lib/python3.11/site-packages/cpyvpn-0.0.0-py3.11.egg/cpyvpn/auth.py", line 407, in init
  File "/usr/local/lib/python3.11/site-packages/cpyvpn-0.0.0-py3.11.egg/cpyvpn/auth.py", line 126, in do_login
  File "/usr/local/lib/python3.11/site-packages/cpyvpn-0.0.0-py3.11.egg/cpyvpn/auth.py", line 164, in _extract_ac
Exception: Authentication error: Access denied - wrong user name or password  (code=101)
'''
