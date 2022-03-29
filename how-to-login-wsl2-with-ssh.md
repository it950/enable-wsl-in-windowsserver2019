# How to login wsl2(ubuntu) with ssh from another computer
1. Install open-ssh

``` bash
sudo apt install openssh-client
sudo apt install openssh-server
```

2. Change port to 22222
``` shell
sudo vim /etc/ssh/sshd_config
```

3. Start ssh server
``` shell
sudo service ssh start
```

4. Port mapping from server to wsl2
``` shell
netsh interface portproxy set v4tov4 listenport=22222 listenaddress=0.0.0.0 connectport=22222 connectaddress=172.21.233.43
```
