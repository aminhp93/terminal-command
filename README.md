

## Commands

* Change mode:
    - `sudo chown -R $USER /var/www/2021-website`

* System Service:
    - `sudo nano /etc/systemd/system/2021-website.service`
    - ```
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
    - `sudo systemctl daemon-reload`
    - `sudo systemctl enable 2021-website.service`
    - `sudo systemctl start 2021-website`
    - `sudo systemctl status 2021-website`


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
