# CLI

tags: #cli #utils


## GPG


```shell
gpg --full-generate-key
gpg --list-secret-keys --keyid-format=long
gpg --armor --export 6E5BF9A995A2F7FBFDD0DFA5F0A76ED9C904D8E0
gpg --armor --export-secret-key 6E5BF9A995A2F7FBFDD0DFA5F0A76ED9C904D8E0
```




### Links:

- [# Generating a new GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)



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

**Forward ssh-agent**


`echo $SSH_AUTH_SOCK`

```
Host some-host-name
	IdentityAgent "~/Library/Group Containers/2BUA8C4S2C.com.1password/t/agent.sock"
	RemoteForward /run/user/1000/gnupg/S.gpg-agent /Users/user/.gnupg/S.gpg-agent.extra
```


**Forward gpg-agent**

Links:

- [GnuPG agent forwarding Gist](https://gist.github.com/TimJDFletcher/85fafd023c81aabfad57454111c1564d)
- [GPG agent forwarding via SSH](https://rabbithole.wwwdotorg.org/2021/03/03/gpg-agent-fwding-over-ssh.html)
- [Forwarding gpg-agent to a remote system over SSH](https://wiki.gnupg.org/AgentForwarding)


`echo "test" | gpg --encrypt -r KEY_NAME|gpg --decrypt`


Troubleshooting:

- In case having an error `gpg: public key decryption failed: No pinentry` just kill gpg-agent on the host machine `killall gpg-agent` and try one more time.
- Can't find your private key on the guest machine? `gpg -K` check if the gpg-agent is running on the guest machine `ps aux|grep gpg-agent`; if yes, kill it and re-ssh.
- Are you still can find the private key on the guest machine? Check the `RemoteForward` on the remote and the local side, also `gpgconf --list-dirs agent-ssh-socket`
- You also need to disable gpg-agent on the guest machine `echo no-autostart|tee -a  ~/.gnupg/gpg.conf`


**Local forwarding**

Any connections from the local 80 port are forwarded to intra.example.com:80

`ssh -L 80:intra.example.com:80 gw.example.com`

**Using gpg key as ssh key**

```sh
$ cat .gnupg/gpg-agent.conf
enable-ssh-support
```


```sh
$ gpg2 -K --with-keygrip
/home/bexelbie/.gnupg/pubring.kbx
------------------------------
sec   rsa2048 2019-03-21 [SC] [expires: 2021-03-20]
      96F33EA7F4E0F7051D75FC208715AF32191DB135
      Keygrip = 90E08830BC1AAD225E657AD4FBE638B3D8E50C9E
uid           [ultimate] Brian Exelbierd
ssb   rsa2048 2019-03-21 [E] [expires: 2021-03-20]
      Keygrip = 5FA04ABEBFBC5089E50EDEB43198B4895BCA2136
ssb   rsa2048 2019-03-21 [A]
      Keygrip = 7710BA0643CC022B92544181FF2EAC2A290CDC0E

$ echo 7710BA0643CC022B92544181FF2EAC2A290CDC0E >> ~/.gnupg/sshcontrol
```

```sh
$ gpgconf --launch gpg-agent
```

```
$ SSH_AUTH_SOCK=$(gpgconf --list-dirs agent-ssh-socket) ssh-add -L
```


```
Host host-support-gpg-ssh
    HostName host-support-gpg-ssh.io
    VisualHostKey yes
    ServerAliveInterval 15
    ServerAliveCountMax 3
    ControlMaster auto
    ControlPersist 10m
    ControlPath /tmp/ssh-%C
    ForwardAgent yes
    RemoteForward /home/%r/.gnupg/S.gpg-agent %d/.gnupg/S.gpg-agent.extra
    StreamLocalBindUnlink yes
    IdentityAgent %d/.gnupg/S.gpg-agent.ssh
```

Get your gpg-ssh public key

```sh
$ gpg --export-ssh-key (whoami)
```

Links:
- [How to enable SSH access using a GPG key for authentication](https://opensource.com/article/19/4/gpg-subkeys-ssh)
- [GPG - SSH setup](https://gist.github.com/mcattarinussi/834fc4b641ff4572018d0c665e5a94d3)

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

Keybinding:

alt+Enter inserts a newline at the cursor position.
Alf+f/b move the cursor one word left or righ.
Shift+← and Shift+→ move the cursor one word left or righ.
Control+D delete one character to the right of the cursor.
Control+W removes the previous path component
Control+X copies the current buffer to the system’s clipboard.
Alt+L lists the contents of the current directory.
Alt+O opens the file at the cursor in a pager.
Alt+P adds the string &| less;
Alt+E edit the current command line in an external editor.
Alt+S Prepends sudo to the current commandline.


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
