TODO
====
## other commands

### cache
로컬 OCI 이미지를 미니쿠베 cache 디렉터리(`~/.minikube/cache`)로 추가/삭제

### addons
- freshpod: 이미지가 변경되면 자동 재시작
- gvisor: a user-space kernel (advanced)
- ingress: nginx ingress
- logviewer: logging
 - minikube v1.9.2/hyperkit 활성화 안됨.
- metrics-server: metrics monitoring

### profile
다른 VM 사용?
- 설정들을 정해놓고 프로파일로 변경해서 사용할 수 있겠음.
 - CPUS, MEM, Runtime, Hypervisor?

```
$ minikube start -p test \
--cpus=2 --memory=4096 \
--container-runtime='containerd'
```

### tunnel
VM안의 ClusterIP를 사용할 수 있는 터널링. 다음과 같이 호스트 머신에서 ClusterIP를 직접 호출할 수 있음:
```
$ curl -k https://10.96.0.1:443 -v
```

### mount
파일시스템 mount, 9p 프로토콜 사용, uid/gid 변경
사용처: ?

### kubectl
클러스터 버전에 맞는 kubectl 사용. 호환에 문제가 있지 않는 이상 호스트에서 사용하는 것이 나을 듯.

## hypervisor
### hyperkit

install: Docker for Mac에서 이미 사용.

minikube start:
```
$ minikube start -p hyperkit \
--cpus=4 --memory=8192 \
--container-runtime='containerd' \
--driver='hyperkit'
```
