# Kerbrute
Ein Tool zum schnellen Erzwingen und Enumerieren gültiger Active Directory-Konten durch Kerberos Pre-Authentication.<br /><br />
Das Bruteforcing von Windows-Passwörtern mit Kerberos ist viel schneller als jeder andere mir bekannte Ansatz und potenziell heimlicher, da Fehler bei der Vorauthentifizierung nicht das "traditionelle" Ereignis **4625** (Ein Konto konnte sich nicht anmelden) auslösen. Mit Kerberos können Sie einen Benutzernamen validieren oder eine Anmeldung testen, indem Sie nur einen UDP-Frame an den KDC (Domain Controller) senden. 

## Installation

```hl:1
$ go get github.com/bbsynapse/kerbrute
```
Kompilieren der Version

```hlt:1,9,21
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
Kopieren der Versionen nach **/opt/kerbrute**

```hl:1,2
sudo mkdir /opt/kerbrute
sudo cp <Verzeichnis mit den Kerbrutedateien> /opt/kerbrute
```

## PATH Variable in Kali  .zshrc setzen

```hl:1
export PATH=$PATH:/opt/kerbrute
```
Aktualisieren der PATH-Variablen

```hl:1
source ./.zshrc 
