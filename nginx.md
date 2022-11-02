## nginx

- Create file

```
sudo nano /etc/nginx/sites-available/2020-website
```

- Content file

```
    server {
        listen 80;
        server_name 54.169.93.240;

        location / {
            include proxy_params;
            proxy_pass http://localhost:3000/;
        }
    }
```

- Link

```
sudo ln -s /etc/nginx/sites-available/2020-website /etc/nginx/sites-enabled
```

- Test 

```
sudo nginx -t
```

- Remove nginx default

```
sudo rm /etc/nginx/sites-enabled/default
```

- Restart

```
sudo service nginx restart
```
