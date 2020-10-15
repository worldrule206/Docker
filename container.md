## 컨테이너(Container) 이해하기 - 격리된 환경에서 실행되는 프로세스

- 이미지를 통해서 컨테이너를 실행
- 컨테이너는 이 파일들의 집합 위에서 실행된 특별한 프로세스
- 컨테이너는 가상머신이라기보다는 프로세스
- 컨테이너는 docker run를 통해서 실행
- shell을 실행하기 위해서 -it를 옵션 사용
- bash 대신 SSH 서버를 실행하고 SSH 클라이언트를 통해서 접속하는 것도 가능
- SSH를 통해 서버에 접속한 것이 아니라, 호스트OS와 격리된 환경에서 bash 프로그램을 실행했다고 이해하는 것이 더 정확
---
```console
$ docker ps   # 현재 실행중인 모든 컨테이너 목록
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
c9147606ecfb        centos:latest       "bash"              26 seconds ago      Up 25 seconds                           goofy_dubinsky

$ docker ps -a    # 실행 및 종료된 모든 컨테이너 목록
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
c9147606ecfb        centos:latest       "bash"              3 minutes ago       Exited (0) 35 seconds ago                       goofy_dubinsky
b02792f6938a        centos:latest       "bash"              4 minutes ago       Exited (0) 3 minutes ago                        gracious_lehmann
773c34738f95        hello-world         "/hello"            2 hours ago         Exited (0) 2 hours ago                          trusting_pike
3c4af30e2522        hello-world         "/hello"            2 hours ago         Exited (0) 2 hours ago                          practical_driscoll
```
---
### 컨테이너 재실행(restart) 및 접속(attach)
```console
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                     PORTS               NAMES
c9147606ecfb        centos:latest       "bash"              7 minutes ago       Exited (0) 5 minutes ago                       goofy_dubinsky
b02792f6938a        centos:latest       "bash"              9 minutes ago       Exited (0) 8 minutes ago                       gracious_lehmann
773c34738f95        hello-world         "/hello"            2 hours ago         Exited (0) 2 hours ago                         trusting_pike
3c4af30e2522        hello-world         "/hello"            2 hours ago         Exited (0) 2 hours ago                         practical_driscoll

$ docker restart c9147606ecfb
c9147606ecfb

$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                     PORTS               NAMES
c9147606ecfb        centos:latest       "bash"              8 minutes ago       Up 1 second                                    goofy_dubinsky
b02792f6938a        centos:latest       "bash"              9 minutes ago       Exited (0) 8 minutes ago                       gracious_lehmann
773c34738f95        hello-world         "/hello"            2 hours ago         Exited (0) 2 hours ago                         trusting_pike
3c4af30e2522        hello-world         "/hello"            2 hours ago         Exited (0) 2 hours ago                         practical_driscoll

test@ubuntu_s:~$ docker attach c9147606ecfb
[root@c9147606ecfb /]#
```
