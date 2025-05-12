# Alist_123
> 实现123网盘无限制下载
- Docker amd64架构部署命令:`docker run -d --restart=unless-stopped -v /etc/alist:/opt/alist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name="alist" xiguanle/alist:latest-aio`
