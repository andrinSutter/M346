# Lab

## IP-Adressen vergeben

Bei unserer Windows-VM vergeben wir die IP-Adresse `192.168.210.2` und bei unserer Linux-VM `192.168.210.3` oder wir beziehen sie über DHCP.

Darüber hinaus müssen wir bei Windows noch die eingehende Regel **Datei- und Druckerfreigabe (Echoanforderung - ICMPv4 eingehend)** aktivieren.

## SSH-Server installieren
Auf der Ubuntu-VM installieren wir nun den SSH-Server:

```Bash
sudo apt-get update
sudo apt-get install openssh-server
```

## Per SSH verbinden

### Passwort

Sobald der SSH-Server installiert wurde, können wir uns per Passwort remote mit der Linux-VM verbinden. Dazu nutzen wir folgendes Kommando auf der Windows-VM:

````Bash
ssh [username]@[remote-ip-address]
````

Nun geben wir noch das Passwort unseres User-Accounts auf der Linux-VM an und schon sind wir remote verbunden.


## Private-/Public-Key

Da das Übertragen von Passwörtern nicht besonders sicher ist, können wir auch ein Schlüsselpaar verwenden. Dafür nutzen wir auf der Windows-VM, also dem SSH-Client folgenden Command:

````Bash
ssh-keygen -t rsa -b 4096
````

Die nachfolgenden Fragen können wir alle mit
Enter
überspringen. Nun haben wir einen Private- und einen Public-Key. 

Den Public Key müssen wir nun an unsere Linux-VM übergeben. Dafür kopieren wir den Schlüssel z.B. mit: 

````Bash
type c:\users\vmadmin\.ssh\id_rsa.pub | ssh vmadmin@192.168.210.22
"cat >> ~/.ssh/authorized_keys"
````

Jetzt können wir uns ohne Passwort uns in die Linux-VM einloggen.

### Passwortauthentifizierung deaktivieren

Um nun den Zugriff über Passwörter komplett zu deaktivieren, müssen wir in der Datei **/etc/ssh/sshd_config** die Zeile `   #PasswordAuthentication` yes durch PasswordAuthentication no ersetzen.