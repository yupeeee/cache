```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

```bash
ssh-copy-id -p PORT_NUMBER USERNAME@REMOTE_SERVER_IP
```

```
Host MY_REMOTE_SERVER
    HostName REMOTE_SERVER_IP
    User USERNAME
    Port PORT_NUMBER
    # IdentityFile ~/.ssh/id_rsa
```

If using ProxyJump:
```bash
ssh-copy-id -o ProxyJump=PROXYJUMP_SERVER MY_REMOTE_SERVER
```

```
Host PROXYJUMP_SERVER
    HostName PROXYJUMP_SERVER_IP
    User USERNAME
    Port PORT_NUMBER
    # IdentityFile ~/.ssh/id_rsa

Host MY_REMOTE_SERVER
    HostName REMOTE_SERVER_IP
    User USERNAME
    ProxyJump PROXYJUMP_SERVER
    # IdentityFile ~/.ssh/id_rsa
```