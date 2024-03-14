#web
# Technologies
Déterminer les outils sur lequel tourne le système 
- recherche des port sur internet
- wappanalyser, burp, nucléi
- recherche de vulnérabilités sur les différents outils (outils maison, outils publique)
- outils publics (ngnix, apache, ...) :
	- recherche de vulnérabilités
	- Possible de faire une mise à jour mais quasiment impossible de modifier le code source.

# Exploration
- client or server side
- source code search (key, password)
- redirection
- http request type
- directory transversal
- http redirection
- 

# Fuzzing
```bash
ffuf -c -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u http://analytical.htb/FUZZ -ic -mc all -fs 162
```

