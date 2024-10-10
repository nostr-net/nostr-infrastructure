# nostr.net infrastructure
## relay.nostr.net
/etc/systemd/system/strfry.service
```
[Unit]
Description=strfry relay service

[Service]
User=strfry
ExecStart=/usr/local/bin/strfry relay
Restart=on-failure
RestartSec=5
ProtectHome=yes
NoNewPrivileges=yes
ProtectSystem=full
#LimitCORE=524288

[Install]
WantedBy=multi-user.target
```

## wot.nostr.net
/etc/systemd/system/wot-relay.service
```
[Unit]
Description=WOT Relay Service
After=network.target

[Service]
ExecStart=/srv/wot-relay/wot-relay
WorkingDirectory=/srv/wot-relay
Restart=always
User=wot
Group=wot
MemoryLimit=5G

[Install]
WantedBy=multi-user.target

```
