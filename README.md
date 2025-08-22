# OpenList_123
> 实现123网盘无限制下载
- Docker部署命令:  <br>
`docker run -d --restart=unless-stopped -v /etc/openlist:/opt/openlist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name="openlist" xiguanle/openlist:latest`

  ClawCloud使用Docker部署可使用lite版本,部署命令:  <br>
  `docker run -d --restart=unless-stopped -v /etc/openlist:/opt/openlist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name="openlist" xiguanle/openlist:latest-lite`
- v4.1.0 以后版本 <br>

  如果您希望使用当前用户运行和管理 OpenList 及其配置目录，请使用以下命令：<br>
  `mkdir -p /etc/openlist`  <br>
  `docker run --user $(id -u):$(id -g) -d --restart=unless-stopped -v /etc/openlist:/opt/openlist/data -p 5244:5244 -e UMASK=022 --name="openlist" xiguanle/openlist:latest`  <br>

  如果您希望使用 1001，即容器内置的默认 openlist 用户运行和管理 OpenList 及其配置目录，请使用以下命令：  <br>
  `mkdir -p /etc/openlist`  <br>
  `sudo chown -R 1001:1001 /etc/openlist`  <br>
  `docker run -d --restart=unless-stopped -v /etc/openlist:/opt/openlist/data -p 5244:5244 -e UMASK=022 --name="openlist" xiguanle/openlist:latest`  <br>

  ClawCloud同理使用Lite版本
