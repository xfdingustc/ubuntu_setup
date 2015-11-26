# ubuntu_setup

## setup ssh
`sudo apt-get install openssh-server`

## setup samba
1. install samba
  ``` shell
  sudo apt-get install samba
  ```
2. make share dir
  ``` shell
cd /opt
mkdir linuxsir
chmod 777 linuxsir
```
3. modify smb.conf
  ``` shell
  sudo vi /etc/samba/smb.conf
  ```
  Add in the tail:
  ``` shell
  [global]
  workgroup = LinuxSir
  netbios name = LinuxSir05
  server string = Linux Samba Server TestServer
  security = share

[linuxsir]
  path = /opt/linuxsir
  writeable = yes
  browseable = yes
  guest ok = yes

  ```
4. restart samba service
  ``` shell
  sudo vi /etc/init.d/samba restart
  ```
 



