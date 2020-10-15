```console
$ docker ps    # 권한 에러 발생
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get http://%2Fvar%2Frun%2Fdocker.sock/v1.40/containers/json: dial unix /var/run/docker.sock: connect: permission denied

$ sudo usermod -aG docker $USER
$ sudo su - $USER

$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
c9147606ecfb        centos:latest       "bash"              26 seconds ago      Up 25 seconds                           goofy_dubinsky
```
