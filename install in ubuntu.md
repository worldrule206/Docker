```console
test@ubuntu_s:~$ su -
Password: 
root@ubuntu_s:~#

root@ubuntu_s:~# sudo apt-get remove docker docker-engine docker.io containerd runc
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Package 'docker-engine' is not installed, so not removed
Package 'docker' is not installed, so not removed
Package 'containerd' is not installed, so not removed
Package 'docker.io' is not installed, so not removed
Package 'runc' is not installed, so not removed
0 upgraded, 0 newly installed, 0 to remove and 18 not upgraded.

root@ubuntu_s:~# sudo apt-get update
Hit:1 http://kr.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://kr.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://kr.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://kr.archive.ubuntu.com/ubuntu bionic-security InRelease
Reading package lists... Done
root@ubuntu_s:~# sudo apt-get install \
>     apt-transport-https \
>     ca-certificates \
>     curl \
>     gnupg-agent \
>     software-properties-common
Reading package lists... Done
Building dependency tree       
Reading state information... Done
ca-certificates is already the newest version (20190110~18.04.1).
ca-certificates set to manually installed.
curl is already the newest version (7.58.0-2ubuntu3.10).
curl set to manually installed.
software-properties-common is already the newest version (0.96.24.32.14).
software-properties-common set to manually installed.
The following NEW packages will be installed:
  apt-transport-https gnupg-agent
0 upgraded, 2 newly installed, 0 to remove and 18 not upgraded.
Need to get 6,568 B of archives.
After this operation, 196 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kr.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 apt-transport-https all 1.6.12ubuntu0.1 [1,692 B]
Get:2 http://kr.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 gnupg-agent all 2.2.4-1ubuntu1.3 [4,876 B]
Fetched 6,568 B in 1s (10.2 kB/s)      
Selecting previously unselected package apt-transport-https.
(Reading database ... 67143 files and directories currently installed.)
Preparing to unpack .../apt-transport-https_1.6.12ubuntu0.1_all.deb ...
Unpacking apt-transport-https (1.6.12ubuntu0.1) ...
Selecting previously unselected package gnupg-agent.
Preparing to unpack .../gnupg-agent_2.2.4-1ubuntu1.3_all.deb ...
Unpacking gnupg-agent (2.2.4-1ubuntu1.3) ...
Setting up apt-transport-https (1.6.12ubuntu0.1) ...
Setting up gnupg-agent (2.2.4-1ubuntu1.3) ...

root@ubuntu_s:~# curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
OK

root@ubuntu_s:~# sudo apt-key fingerprint 0EBFCD88
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]

root@ubuntu_s:~# sudo apt-get update
Hit:1 http://kr.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://kr.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://kr.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://kr.archive.ubuntu.com/ubuntu bionic-security InRelease
Reading package lists... Done
root@ubuntu_s:~# sudo apt-get install docker-ce docker-ce-cli containerd.io
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Package docker-ce is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'docker-ce' has no installation candidate
E: Unable to locate package docker-ce-cli
E: Unable to locate package containerd.io
E: Couldn't find any package by glob 'containerd.io'
E: Couldn't find any package by regex 'containerd.io'
root@ubuntu_s:~# apt-cache madison docker-ce
root@ubuntu_s:~# sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
-su: VERSION_STRING: No such file or directory

root@ubuntu_s:~# sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
Hit:1 http://kr.archive.ubuntu.com/ubuntu bionic InRelease                  
Get:2 https://download.docker.com/linux/ubuntu bionic InRelease [64.4 kB]   
Get:3 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages [13.0 kB]
Hit:4 http://kr.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:5 http://kr.archive.ubuntu.com/ubuntu bionic-backports InRelease      
Hit:6 http://kr.archive.ubuntu.com/ubuntu bionic-security InRelease
Fetched 77.4 kB in 1s (58.6 kB/s)
Reading package lists... Done

root@ubuntu_s:~# sudo apt update -y
Hit:1 https://download.docker.com/linux/ubuntu bionic InRelease
Hit:2 http://kr.archive.ubuntu.com/ubuntu bionic InRelease                         
Hit:3 http://kr.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:4 http://kr.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:5 http://kr.archive.ubuntu.com/ubuntu bionic-security InRelease
Reading package lists... Done
Building dependency tree       
Reading state information... Done
18 packages can be upgraded. Run 'apt list --upgradable' to see them.

root@ubuntu_s:~# sudo apt install -y docker-ce
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  aufs-tools cgroupfs-mount containerd.io docker-ce-cli libltdl7 pigz
The following NEW packages will be installed:
  aufs-tools cgroupfs-mount containerd.io docker-ce docker-ce-cli libltdl7 pigz
0 upgraded, 7 newly installed, 0 to remove and 18 not upgraded.
Need to get 91.3 MB of archives.
After this operation, 410 MB of additional disk space will be used.
Get:1 https://download.docker.com/linux/ubuntu bionic/stable amd64 containerd.io amd64 1.3.7-1 [24.4 MB]
Get:2 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 pigz amd64 2.4-1 [57.4 kB]
Get:3 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 aufs-tools amd64 1:4.9+20170918-1ubuntu1 [104 kB]
Get:4 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 cgroupfs-mount all 1.4 [6,320 B]
Get:5 http://kr.archive.ubuntu.com/ubuntu bionic/main amd64 libltdl7 amd64 2.4.6-2 [38.8 kB]
Get:6 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce-cli amd64 5:19.03.13~3-0~ubuntu-bionic [44.2 MB]
Get:7 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce amd64 5:19.03.13~3-0~ubuntu-bionic [22.5 MB]
Fetched 91.3 MB in 8s (11.3 MB/s)                                                                              
Selecting previously unselected package pigz.
(Reading database ... 67151 files and directories currently installed.)
Preparing to unpack .../0-pigz_2.4-1_amd64.deb ...
Unpacking pigz (2.4-1) ...
Selecting previously unselected package aufs-tools.
Preparing to unpack .../1-aufs-tools_1%3a4.9+20170918-1ubuntu1_amd64.deb ...
Unpacking aufs-tools (1:4.9+20170918-1ubuntu1) ...
Selecting previously unselected package cgroupfs-mount.
Preparing to unpack .../2-cgroupfs-mount_1.4_all.deb ...
Unpacking cgroupfs-mount (1.4) ...
Selecting previously unselected package containerd.io.
Preparing to unpack .../3-containerd.io_1.3.7-1_amd64.deb ...
Unpacking containerd.io (1.3.7-1) ...
Selecting previously unselected package docker-ce-cli.
Preparing to unpack .../4-docker-ce-cli_5%3a19.03.13~3-0~ubuntu-bionic_amd64.deb ...
Unpacking docker-ce-cli (5:19.03.13~3-0~ubuntu-bionic) ...
Selecting previously unselected package docker-ce.
Preparing to unpack .../5-docker-ce_5%3a19.03.13~3-0~ubuntu-bionic_amd64.deb ...
Unpacking docker-ce (5:19.03.13~3-0~ubuntu-bionic) ...
Selecting previously unselected package libltdl7:amd64.
Preparing to unpack .../6-libltdl7_2.4.6-2_amd64.deb ...
Unpacking libltdl7:amd64 (2.4.6-2) ...
Setting up aufs-tools (1:4.9+20170918-1ubuntu1) ...
Setting up containerd.io (1.3.7-1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
Setting up cgroupfs-mount (1.4) ...
Setting up libltdl7:amd64 (2.4.6-2) ...
Setting up docker-ce-cli (5:19.03.13~3-0~ubuntu-bionic) ...
Setting up pigz (2.4-1) ...
Setting up docker-ce (5:19.03.13~3-0~ubuntu-bionic) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
Processing triggers for libc-bin (2.27-3ubuntu1.2) ...
Processing triggers for systemd (237-3ubuntu10.42) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for ureadahead (0.100.0-21) ...

root@ubuntu_s:~# apt-cache madison docker-ce
 docker-ce | 5:19.03.13~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.12~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.11~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.10~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.9~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.8~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.7~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.6~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.5~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.4~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.3~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.2~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.1~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:19.03.0~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.9~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.8~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.7~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.6~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.5~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.4~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.3~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.2~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.1~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 5:18.09.0~3-0~ubuntu-bionic | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 18.06.3~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 18.06.2~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 18.06.1~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 18.06.0~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
 docker-ce | 18.03.1~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages

root@ubuntu_s:~# sudo systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Wed 2020-10-14 05:27:07 UTC; 38s ago
     Docs: https://docs.docker.com
 Main PID: 3885 (dockerd)
    Tasks: 10
   CGroup: /system.slice/docker.service
           └─3885 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.074024584Z" level=warning msg="Your kernel doe
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.074230294Z" level=warning msg="Your kernel doe
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.074329458Z" level=warning msg="Your kernel doe
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.074578234Z" level=info msg="Loading containers
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.385629585Z" level=info msg="Default bridge (do
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.618185707Z" level=info msg="Loading containers
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.692201688Z" level=info msg="Docker daemon" com
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.692295729Z" level=info msg="Daemon has complet
Oct 14 05:27:07 ubuntu_s dockerd[3885]: time="2020-10-14T05:27:07.752693629Z" level=info msg="API listen on /var
Oct 14 05:27:07 ubuntu_s systemd[1]: Started Docker Application Container Engine.

root@ubuntu_s:~# docker version
Client: Docker Engine - Community
 Version:           19.03.13
 API version:       1.40
 Go version:        go1.13.15
 Git commit:        4484c46d9d
 Built:             Wed Sep 16 17:02:36 2020
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          19.03.13
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.13.15
  Git commit:       4484c46d9d
  Built:            Wed Sep 16 17:01:06 2020
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.3.7
  GitCommit:        8fba4e9a7d01810a393d5d25a3621dc101981175
 runc:
  Version:          1.0.0-rc10
  GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683

root@ubuntu_s:~# sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete 
Digest: sha256:4cf9c47f86df71d48364001ede3a4fcd85ae80ce02ebad74156906caff5378bc
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
