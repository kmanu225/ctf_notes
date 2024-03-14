#telnet

# common users
```ruby
root
admin
administrator
anonymous
```

# telnet (23)
Permet de faire de l'administration à distance.
Problème: les mots de passe circule en clair.

![[Pasted image 20240311061418.png]]

# ftp (21)
Permet de faire du partage de fichier entre deux machines.
Problème: les fichiers sont envoyées en clair même après authentification -> utiliser ftps (ftp dans ssl/tls) ou sftp (ftp via ssh, chiffrement à l'envoie et déchiffrement à la réception).
![[Pasted image 20240311062124.png]]
- anonymous & passwd anything 



# smb (445)
Permet de partager des fichiers entre un client et un serveur. Une zone de stockage est appelée share.
![[Pasted image 20240311055958.png]]

- smbclient: 
	- interagir avec un server smb
	- tenter une connexion sans mot de passe
- lister les shares (smb -L)
- se connecter à un share (`smbclient \\\\{target_ip}\\{share}`)
