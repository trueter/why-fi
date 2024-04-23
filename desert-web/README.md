Set up this service by placing 
```
[Service]
WorkingDirectory=/home/whynot/why-fi/desert-web
ExecStart=python -m http.server 80
Restart=always
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=propanel
User=root
Group=root
[Install]
WantedBy=multi-user.target
```
into `/etc/systemd/system`