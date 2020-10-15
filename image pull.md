## 도커 이미지 사용

- 도커 레지스트리의 centos 이미지를 pull(다운 받기)
- 이미지는 파일들의 집합
- 이미지는 불변(Immutable)한 저장 매체
---
```console
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              bf756fb1ae65        9 months ago        13.3kB

$ docker pull centos
Using default tag: latest
latest: Pulling from library/centos
3c72a8ed6814: Pull complete 
Digest: sha256:76d24f3ba3317fa945743bb3746fbaf3a0b752f10b10376960de01da70685fbd
Status: Downloaded newer image for centos:latest
docker.io/library/centos:latest

$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
centos              latest              0d120b6ccaa8        2 months ago        215MB
hello-world         latest              bf756fb1ae65        9 months ago        13.3kB
```
---
### 도커 허브(Docker Hub) - 공식 이미지 레지스트리
```console
$ docker info | grep Registry
WARNING: No swap limit support
 Registry: https://index.docker.io/v1/
```
