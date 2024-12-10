# Kerbrute

Ein Tool zum schnellen Erzwingen und Aufzählen gültiger Active Directory-Konten durch Kerberos Pre-Authentication.

Das Bruteforcing von Windows-Passwörtern mit Kerberos ist viel schneller als jeder andere mir bekannte Ansatz und potenziell heimlicher, da Fehler bei der Vorauthentifizierung nicht das "traditionelle" Ereignis **4625** (Ein Konto konnte sich nicht anmelden) auslösen. Mit Kerberos können Sie einen Benutzernamen validieren oder eine Anmeldung testen, indem Sie nur einen UDP-Frame an den KDC (Domain Controller) senden. 

## Installation
Du kannst das letzte [Release downloaden](https://github.com/BBSynapse/Kerbrute/releases/tag/kerbrute) oder nachfolgend auch direkt mit Go installieren:

```
$ go get github.com/ropnop/kerbrute
```

With the repository cloned, you can also use the Make file to compile for common architectures:

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

