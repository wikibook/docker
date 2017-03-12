이미지를 직접 빌드할 수 있는 Dockerfile입니다.
----
책에서 사용되는 이미지를 직접 빌드할 수 있습니다.

1. chapter2
   * "2.2.8.3 fluentd 로깅" 절에서 사용되는 **alicek106/fluentd:mongo** 이미지
2. chapter6
   * "6.2.4.1 NFS 서버 설치" 절의 **alicek106/ubuntu-nfs-server:0.0** 이미지

#### 사용 방법
(1) 이 저장소를 복사합니다.
```bash
# git clone https://github.com/wikibook/docker.git
Cloning into 'docker'...
warning: You appear to have cloned an empty repository.
Checking connectivity... done.
```

(2) 이미지를 빌드합니다. 아래의 예시는 **reader/fluentd:mongo** 라는 이름의 이미지를 빌드합니다.
```bash
# cd docker && ls
chapter2  chapter6  README.md

# cd chapter2/fluentd_mongo
# docker build ./ -t reader/fluentd:mongo
Step 1/9 : FROM fluent/fluentd:v0.14.12
v0.14.12: Pulling from fluent/fluentd
....
Removing intermediate container 9910c50a5d44
Successfully built a4a1bb56ed5a
```

(3) 빌드된 이미지를 확인합니다.
```bash
# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
reader/fluentd      mongo               a4a1bb56ed5a        8 minutes ago       144 MB
....
```

