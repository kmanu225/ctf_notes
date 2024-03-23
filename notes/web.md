![[Pasted image 20240315111713.png]]
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
- http request type
- directory transversal
- http redirection

# Broken access control
- path transversal: 
	- robots.txt
	- gobuster
	- code source
	- forge url parameter or field
- horizontal or vertical escalation:
	- IDOR: insecure direct object reference
		- reused somewhere
	- cookie (locally, interception), 

# Authentication & Identification
- credential disclosure
- common credentials
- user enumeration:
	- status code
	- error messages
	- response time
- authentication before validation

# SSRF (Server-side request forgery)
Use the server to make some request on internal ressources.
- usually no authentication is required when a server make a request on this kind of ressources
- target a protected page
- target network node

# File upload
Consequences: DoS (upload large file), overwrite file, get shell

**Technics**
1. What is forbidden ?
2. What are the right of an uploaded file ?
3. How to access uploaded file ?
4. blacklists 
	- `.htaccess` : modify it
	- extension obfuscation: `.php.jpg, .php., %2Ephp, .asp;.jpg, .asp%00.jpg`, `xC0 x2E`, `xC4 xAE` or `xC0 xAE`, `.p.phphp`
5. upload via url -> downloading the image
6. name via pseudo random functions
7. upload xml -> XSS
8. upload .doc, .xls -> XXE
9. use put if no upload function is available


**Prevent**
- check file extension  -> whitelist
- check mime -> can be modify
- set rights in the directory where it is uploaded
- prevent access to dangerous files: strip extension
- check the content of the uploaded file :
	- magic number 
	- inefficient for polyglot file
- prevent directory transversal
- use framework
	- modify name randomly -> prevent overwrite
	- validation in sandbox
- use anti-virus -> race condition for detecting the malicious file

# SQLi