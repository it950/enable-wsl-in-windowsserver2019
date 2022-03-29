# Install OpenSSH on windows 10
1. (Install OpenSSH)[https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse]
2. Generate key: ``ssh-keygen``
3. Copy ssh key for standard user

``` bash
# Make sure that the .ssh directory exists in your server's user account home folder
ssh username@domain1@contoso.com mkdir C:\Users\username\.ssh\

# Use scp to copy the public key file generated previously on your client to the authorized_keys file on your server
scp C:\Users\username\.ssh\id_ed25519.pub user1@domain1@contoso.com:C:\Users\username\.ssh\authorized_keys
```

4. Copy ssh key for Administrator user
``` bash
# Make sure that the .ssh directory exists in your server's user account home folder
ssh user1@domain1@contoso.com mkdir C:\ProgramData\ssh\

# Use scp to copy the public key file generated previously on your client to the authorized_keys file on your server
scp C:\Users\username\.ssh\id_ed25519.pub user1@domain1@contoso.com:C:\ProgramData\ssh\administrators_authorized_keys

# Appropriately ACL the authorized_keys file on your server
# You can copy the public key to Windows 10 directly, and then open the file property, assign Administrators and SYSTEM to the file in security tab
ssh --% user1@domain1@contoso.com icacls.exe "C:\ProgramData\ssh\administrators_authorized_keys" /inheritance:r /grant "Administrators:F" /grant "SYSTEM:F"
```
