# Kerbrute

Ein Tool zum schnellen Erzwingen und Aufzählen gültiger Active Directory-Konten durch Kerberos Pre-Authentication.

Das Bruteforcing von Windows-Passwörtern mit Kerberos ist viel schneller als jeder andere mir bekannte Ansatz und potenziell heimlicher, da Fehler bei der Vorauthentifizierung nicht das "traditionelle" Ereignis **4625** (Ein Konto konnte sich nicht anmelden) auslösen. Mit Kerberos können Sie einen Benutzernamen validieren oder eine Anmeldung testen, indem Sie nur einen UDP-Frame an den KDC (Domain Controller) senden. 

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

## Kerbrute Installation
Du kannst das letzte [Release downloaden](https://github.com/BBSynapse/Kerbrute/releases/tag/kerbrute) oder nachfolgend auch direkt mit Go installieren:

```
$ go get github.com/BBSynapse/kerbrute
```
Wenn das Repository geklont ist, können Sie auch die Make-Datei verwenden, um es für die gängigen Architekturen zu kompilieren:

```
$ make help
help:            Show this help.
windows:  Make Windows x86 and x64 Binaries
linux:  Make Linux x86 and x64 Binaries
mac:  Make Darwin (Mac) x86 and x64 Binaries
clean:  Delete any binaries
all:  Make Windows, Linux and Mac x86/x64 Binaries

$ make all
Done.
Building for windows amd64..
Building for windows 386..
Done.
Building for linux amd64...
Building for linux 386...
Done.
Building for mac amd64...
Building for mac 386...
Done.

$ ls dist/
kerbrute_darwin_386        kerbrute_linux_386         kerbrute_windows_386.exe
kerbrute_darwin_amd64      kerbrute_linux_amd64       kerbrute_windows_amd64.exe
```
### Kopieren der Versionen nach **/opt/kerbrute**

```hl:1,2
sudo mkdir /opt/kerbrute
sudo cp <Verzeichnis mit den Kerbrutedateien> /opt/kerbrute
```
### PATH Variable in Kali  ~/.zshrc setzen

```hl:1
export PATH=$PATH:/opt/kerbrute
```

Aktualisieren der PATH-Variablen

```hl:1
source ./.zshrc 
```
