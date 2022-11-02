

## System service

- Create file

```
sudo nano /etc/systemd/system/2021-website.service
```

- Content file

```
    [Unit]
    Description=2021-website
    After=syslog.target

    [Service]
    WorkingDirectory=/var/www/2021-website/
    ExecStart=/usr/local/bin/npm start
    Restart=always
    StandardInput=null
    StandardOutput=syslog
    StandardError=syslog
    SyslogIdentifier=%n
    KillMode=mixed
    TimeoutStopSec=5
    User=ubuntu

    [Install]
    WantedBy=multi-user.target
```

- Reload

```
sudo systemctl daemon-reload
```

- Enable

```
sudo systemctl enable 2021-website.service
```

- Start

```
sudo systemctl start 2021-website
```

- Check status

```
sudo systemctl status 2021-website
```


* Nginx:
    - `sudo nano /etc/nginx/sites-available/2020-website`
    - ```
        server {
            listen 80;
            server_name 54.169.93.240;

            location / {
                include proxy_params;
                proxy_pass http://localhost:3000/;
            }
        }
        ```
    - `sudo ln -s /etc/nginx/sites-available/2020-website /etc/nginx/sites-enabled`
    - `sudo nginx -t`
    - `sudo rm /etc/nginx/sites-enabled/default`
    - `sudo service nginx restart`


* Server
    - `sudo apt-get update`
    - `sudo apt-get install nginx git python3-venv`


* Poetry
    - `curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python3`
    - `source $HOME/.poetry/env`

* Redis
    - Install redis in /home/ubuntu
    - `wget http://download.redis.io/redis-stable.tar.gz`
    - `tar xvzf redis-stable.tar.gz`
    - `sudo apt install redis-server`
    - `redis-server`

* Postgres
    - `sudo apt install postgresql-client-common`
    - `sudo apt-get install postgresql-client`
    - `sudo apt update`
    - `sudo apt install postgresql postgresql-contrib`
    - Access:
        - `sudo -i -u postgres`
        - `psql`
        - Direct way:
            - `sudo -u postgres psql`

        - `CREATE ROLE ubuntu superuser;`
        - `ALTER ROLE ubuntu with LOGIN;`
