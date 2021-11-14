# SSH

**Local forwarding**

Any connections from the local 80 port are forwarded to intra.example.com:80

`ssh -L 80:intra.example.com:80 gw.example.com`

**Remote forwarding**

Any connections to public.example.com:8080 are forwarded to local 80

`ssh -R 8080:localhost:80 public.example.com`

Forward multiple ports

`ssh -R 80:localhost:8080 -R 443:localhost:8443 root@internal.example.com`

Notes:

Option `GatewayPorts yes` should be enabled there _/etc/ssh/sshd_config_.