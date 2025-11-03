# friends-in-matrix

Grep and replace on repository

1 api_keys
```
111ea560574baaabbbccc9cf2f4d3111
11122233359c0d83f836055e267255674e39f9237dd22fcc5ed444f333222111

strong_password_here_12345
```
2 ip
```
44.333.222.111 - change ip in yours. 
```

3 domains
```
mydomain.com - matrix server(domain)
chat.mydomain.com - matrix chat server(domain)
livekit.mydomain.com - livekit server(domain)
jwt.mydomain.com - jwt server(domain)
```

## Disclaimer: It's not ideal. It works, but it's have problems, i think in default.conf: Excessive parts of nginx.conf and docker-compose.yml..

1) ### uncomment certbot section in docker-compose.yml 
2) ### uncomment section with port 80 and comment others in nginx.conf
    Because of certbot we need to use port 80. In 443 sections we use paths to certs, that at that moment doesn't exist.
3) ### create by certbot certs. 
    ```docker-compose run --rm certbot certonly --webroot -w /var/www/certbot  -d mydomain.com -d chat.mydomain.com -d call.mydomain.com -d livekit.mydomain.com -d jwt.mydomain.com --email email@gmail.com --agree-tos --non-interactive --expand```
4) ### uncomment sections with 443 in nginx.conf
5) ### I prefer to comment certbot in docker-compose.yml 
6) ### docker-compose up -d
