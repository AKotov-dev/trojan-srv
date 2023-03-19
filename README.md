# trojan-srv - personal security server
+ Install the `rpm` or `deb` package on your VPS
+ Generate a personal `server.json` on your computer and connection string using `trojan-srv-gen`
+ Copy `server.json` to VPS `/etc/trojan-srv/server.json` and restart: `systemctl restart trojan-srv`
+ Copy the connection string from `trojan-srv` and paste it into [XRayGUI](https://github.com/AKotov-dev/XRayGUI); Press `Start`
+ Enable the Socks5 proxy - `127.0.0.1:1080` in the browser on your computer
+ This completes the configuration of the secure connection

![](https://raw.githubusercontent.com/AKotov-dev/trojan-srv/main/ScreenShot1.png)

**Note:** The time on the client and server must be synchronized. The time zone does not matter. Tested in Mageia-8/9, Fedora-36 and Ubuntu-22.04. Don't forget to open the ports in `iptables`.  
  
Similar project: [SS-Obfuscator](https://github.com/AKotov-dev/SS-Obfuscator), [vmess-ws](https://github.com/AKotov-dev/vmess-ws).
