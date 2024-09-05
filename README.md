# SSH Cheatsheet


IP Adressen
----------------
Windows: ipconfig
Linux: ip addr
Router: ifconfig

Ping
----------------
Windows: ping {linux Ip}
Linux: ping {windows Ip}

SSH server (Linux)

----------------
`sudo apt-get update`

`sudo apt-get install openssh-server`

`sudo service ssh status`


SSH verbindung mit passwort
----------------
Windows: `ssh benutzer@linuxIp`, antworten mit Yes

SSH verbindung mit Public Key
----------------
`ssh-keygen`
`type ~/.ssh/id_rsa.pub | ssh [username]@[hostname] "cat >> .ssh/authorized_keys"`
oder copy paste 

`ssh-i c:\pfad\zu\id_rsa @a.b.c.d`

Zugang mit passwort deaktivieren
----------------
`sudo nano /etc/ssh/sshd_config`

`PasswordAuthentification` auf no setzen und Kommentar entfernen

`sudo service ssh restart` service restarten damit die configuration übernommen wird

Um zu Testen, ob der Zugang mit Passwort ausgeschaltet ist, können Sie Datei authorized_keys kurz zeitig umbenennen und versuchen sich erneut von WP1 aus anzumelden: ssh vmadmin@a.b.c.d. Dies sollte nun nicht mehr möglich sein.