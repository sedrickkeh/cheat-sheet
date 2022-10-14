# SSH Using RSA Keys
(Guide taken from https://stackoverflow.com/questions/66113731/how-to-save-ssh-password-to-vscode)

1. On local machine, create a public/private RSA key pair:
```bash
ssh-keygen -t rsa
```

2. On local machine, in `~/.ssh/config`, add the following lines:
```bash
Host (server-name)
  HostName (server-name)
  User (user)
  PreferredAuthentications publickey
  IdentityFile "~/.ssh/(name-of-rsa-private-key)"
```

3. On the remote server, copy over the public key to ` <remoteuserhome>/.ssh/authorized_keys`
- If it exists already, you need to add the contents of `<myhost>_rsa.pub` to the end of the file.
- If it does not exist you can use the `<myhost>_rsa.pub` and rename it to `authorized_keys` with permissions of 600.

4. On your local machine, run 
```bash
ssh-agent bash
ssh-add ~/.ssh/(name-of-rsa-private-key)
```