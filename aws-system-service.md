## Server AWS System service

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
