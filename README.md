- NotionNext Blog
- Forked from [tangly1024/NotionNext](https://github.com/tangly1024/NotionNext)
- 此仓库对应服务器主站 : https://www.dalechu.cn/ 和 Vercel 站 https://for.epicurus.fun/
- [试验仓库](https://github.com/Dalecuc/NotionNext) 对应 Vercel 镜像站 : https://www.epicurus.fun
---
<br/>

<p align="center">
    <b>在 Docker 上部署</b>
</p>

Debian 安装 docker :
```shell
apt update && apt install -y docker.io docker-compose jq
```

docker 换源, 自行写入最新可用镜像 :
```shell
vim /etc/docker/daemon.json
```


<br/>

拉取 [我的 NotionNext 镜像](https://github.com/daleveral/NotionNext/pkgs/container/notionnext) :

常规 : 

```shell
docker pull ghcr.io/daleveral/notionnext:main  
```

加速镜像 : 

```shell
docker pull ghcr.linkos.org/daleveral/notionnext:main
```

<br/>

镜像重命名 :
```shell
docker tag ghcr.linkos.org/daleveral/notionnext:main notionnext:latest 
```

```shell
docker images
docker rmi ghcr.linkos.org/daleveral/notionnext:main
docker images
```

<br/>


创建和运行容器 :
```shell
docker run --name NotionNext -d -p=3000:3000 notionnext:latest 
```

