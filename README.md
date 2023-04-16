# Container Compose

使容器部署变得快速简单.


## 前提条件

- docker 和 docker-composer 环境
- podman 和 podmain-compose 环境

二选一

### 一键脚本

Docker
```
bash <(curl -sSL https://gitee.com/SuperManito/LinuxMirrors/raw/main/DockerInstallation.sh)
```
脚本来之: https://github.com/SuperManito/LinuxMirrors

Podman
```
还没时间写
```

### 手动安装脚本

Docker

Podman

https://podman.io/
https://github.com/containers/podman
https://github.com/containers/podman-compose

## 使用

使用 DownGit 下载子目录的打包文件

解压下载的文件
```
unzip download.zip
```

进入文件夹
```
docker-compose up -d
```

运行指定版本
```
docker-compose -f compose.yml up -d
```


## 支持的应用