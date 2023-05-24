[Tier0](https://github.com/johnie123456789/Hack_The_Box_note/blob/main/Start_point.md#tier0)
[Tier1](https://github.com/johnie123456789/Hack_The_Box_note/blob/main/Start_point.md#tier1)
[Tier2](https://github.com/johnie123456789/Hack_The_Box_note/blob/main/Start_point.md#tier2)
# Tier0
## Meow

+  連VPN(用Kali OR Parrot)
   ```
   sudo openvpn + XXX.ovpn
   ```
+  開機
1. Virtual Machine
2. terminal
3. openvpn
4. tun
5. ping
   ```
   ping IP
   ```
6. nmap
   ```
   nmap -sV IP 
   ```
7. telnet
   ```
   telnet IP
   ```
8. root
9. cat
   ```
   cat flag.txt
   ```

## Fawn
1. File Transfer Protocol
2. 21
3. SFTP
4. ping
5. nmap (Thanks)
   ```
   nmap -sV IP 
   ```
6. nmap
   ```
   nmap -sV IP 
   ```
7. ftp -h
8. anonymous
9.  230
10. ls
11. get
12. 退出並cat flag
   ```
   close
   exit
   cat flag.txt
   ```

## Dancing
1. Server Message Block
2. 445
3. microsoft-ds
4. -L
5. smbclient -L IP
6. WorkShares
7. get
8. smbclient \\\\IP\\WorkShares
   多逛逛，多get，就會有flag了

## Redeemer
1. 6379
   ```
   nmap -sV  -p- 10.129.18.32 -min-rate 5000

   ```
2. redis
3. In-memory Database
4. redis-cli
5. -h
6. 連線
   ```
   redis-cli -h 10.129.18.32
   ```
7. info
8. select
9. 4
10. keys *
11. get flag
# Tier1
# Tier2
