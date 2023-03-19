# trojan-srv - personal security server
+ Install the `rpm` or `deb` package on your VPS
+ Generate a personal `server.json` on your computer and connection string using `trojan-srv-gen`
+ Copy `server.json` to VPS `/etc/trojan-srv/server.json` and restart: `systemctl restart trojan-srv`
+ Copy the connection string from `trojan-srv` and paste it into [XRayGUI](https://github.com/AKotov-dev/XRayGUI); Press `Start`
+ Enable the Socks5 proxy - `127.0.0.1:1080` in the browser on your computer
+ This completes the configuration of the secure connection

The server uses a self-signed certificate for 10 years. This is not necessary, but if you have a desire, you can do others:
```
cd /etc/trojan-srv && openssl genrsa -out key.pem 2048

# The answers to all the questions when creating the next key may be empty,
# except specifying the server name. As the server name, specify example.com
openssl req -new -x509 -key key.pem -out cert.pem -days 4095
```
![](https://raw.githubusercontent.com/AKotov-dev/trojan-srv/main/ScreenShot1.png)

If you want to use IPV6 + `trojan-srv`, you can read this article: [How to Install Trojan on IPv6 VPS](https://wiki.hax.co.id/ipv6-servers/how-to-install-trojan-on-ipv6-vps/).

Tested in Mageia-8/9, Fedora-36 and Ubuntu-22.04. Don't forget to open the ports in `iptables`.  
  
Similar project: [SS-Obfuscator](https://github.com/AKotov-dev/SS-Obfuscator), [vmess-ws](https://github.com/AKotov-dev/vmess-ws).
