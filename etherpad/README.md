Set up this service by placing 
```
[Unit]
Description=Etherpad service
After=docker.service
Requires=docker.service

[Service]
Type=oneshot
RemainAfterExit=yes
ExecStart=/bin/bash -c "docker compose -f /home/whynot/why-fi/etherpad/docker-compose.yml up --detach"
ExecStop=/bin/bash -c "docker compose -f /home/whynot/why-fi/etherpad/docker-compose.yml stop"
User=root
Group=root

[Install]
WantedBy=multi-user.target
```
into `/etc/systemd/system/etherpad.service`
