# CLI

tags: #cli #utils

## Send SIGQUIT to quit the process and perform a core dump

`kill -SIGQUIT 8518`

## mitmproxy

Disable mouse

`mitmproxy --set console_mouse=false`

Links:

- [Viewing network traffic calls on IOS real device using MITM Proxy](https://automationhacks.medium.com/viewing-network-traffic-calls-on-ios-real-device-using-mitm-proxy-e413c556466d)
- [How to Man in the Middle HTTPS Using mitmproxy](https://earthly.dev/blog/mitmproxy/)

## dig

**Show TXT records in domain**

`dig -t txt +short  example.com @1.1.1.1`

**Show hide TXT records, for ACME challange**

`dig +short txt _acme-challenge.test3.sg1.example.com @1.1.1.1`

**Show NS records**

`dig +short NS example.com`

**Show traces**

`dig google.com +trace`

Links:

- [DNS Basics and Building Simple DNS Server in Go](https://medium.com/@openmohan/dns-basics-and-building-simple-dns-server-in-go-6cb8e1cfe461)

## ssh

**Forward gpg-agent**

Links:

- [GPG agent forwarding via SSH](https://rabbithole.wwwdotorg.org/2021/03/03/gpg-agent-fwding-over-ssh.html)
- [Forwarding gpg-agent to a remote system over SSH](https://wiki.gnupg.org/AgentForwarding)

`echo "test" | gpg --encrypt -r KEY_NAME|gpg --decrypt`

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

## tcpdump

**Find all GET requests**

`tcpdump -i lo0 port 7089 -vvAls0|rg GET`

## zsh

**Working with history**

`history [first] [last]`

Get all commands in the history `history 0`
Get last 10 commands in the history `history -10`

## fish

**Problem with alt and iterm2**

[solution](https://github.com/fish-shell/fish-shell/issues/7440)

**Change default shell**

`chsh -s /usr/local/bin/fish`

Don't forget add fish to shells here /etc/shells

**help**

`help`

## networkQuality (macOS)

`networkQuality`

## aws

**Loging into ECR**

`aws ecr get-login-password | docker login --username AWS --password-stdin 664818258905.dkr.ecr.ap-southeast-1.amazonaws.com`

## git

**go get results in 'terminal prompts disabled' error for github private repo**

`git config --global --add url."git@github.com:".insteadOf "https://github.com/"`

**How to get the current branch name in Git?**
`git rev-parse --abbrev-ref HEAD`

## kubectl

**Proxy port**

`kubectl port-forward klit-bee-55c74f4b88-hvcpt 2112:2112`

## python

**How to run simple http server?**

`python3 -m http.server -d $(pwd) 8081`

## scutil

**Change hostname**

`sudo scutil --set HostName server1.mynetwork.com`

## migrate

**Dirty database version 1. Fix and force version**

`update schema_migrations set dirty=0, version=CHANGE_FOR_LATEST`

## lsof

**Find who is listenning a port**

`lsof -nP -i4TCP:8081`

## vim

Arrow keys don't work

`:set nocompatible`
`echo "set nocompatible" >> ~/.exrc`
`echo "set nocompatible" >> ~/.vimrc`


## bash

**Tiny HTTP server**

```bash
#!/bin/bash

trap "echo Exited!; exit;" SIGINT SIGTERM

PORT="${1:-1337}"

main () {
    echo "Starting..."

    while true 
    do
        printf 'HTTP/1.1 200 OK\n\n%s' "$(cat index.html)" | nc -c -l ${PORT}
    done
}

main
```