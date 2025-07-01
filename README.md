# OpenList_123
> 实现123网盘无限制下载
- Docker部署命令:`docker run -d --restart=unless-stopped -v /etc/openlist:/opt/openlist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name="openlist" xiguanle/openlist:latest`  
ClawCloud使用Docker部署可使用lite版本,部署命令:`docker run -d --restart=unless-stopped -v /etc/openlist:/opt/openlist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name="openlist" xiguanle/openlist:latest-lite`

- 支持架构:
  - linux/amd64
  - linux/arm64
- 未经测试
  - linux/386
  - linux/s390x
  - linux/riscv64
  - linux/ppc64le
  - linux/arm/v7
  - linux/arm/v6
