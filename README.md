# OpenList_123

> 实现 123 网盘无限制下载（可下载20G以上的大文件）

> [!NOTE]
> 一个月只有20GB流量，能转存的尽量转存吧。(请求下载链接不消耗流量，先将所有文件的链接保存下来后，再转存，当消耗20G流量后将无法请求链接了)

## 部署指南

### 快速开始 (Docker)

**标准版**

```bash
docker run -d --restart=unless-stopped \
  -v /etc/openlist:/opt/openlist/data \
  -p 5244:5244 \
  -e PUID=0 \
  -e PGID=0 \
  -e UMASK=022 \
  --name="openlist" \
  xiguanle/openlist:latest
```

**Lite 版 (适用于 ClawCloud 等)**

```bash
docker run -d --restart=unless-stopped \
  -v /etc/openlist:/opt/openlist/data \
  -p 5244:5244 \
  -e PUID=0 \
  -e PGID=0 \
  -e UMASK=022 \
  --name="openlist" \
  xiguanle/openlist:latest-lite
```

### v4.1.0 及以后版本

**方式一：使用当前用户运行**

如果您希望使用当前用户运行和管理 OpenList 及其配置目录：

```bash
mkdir -p /etc/openlist
docker run --user $(id -u):$(id -g) -d --restart=unless-stopped \
  -v /etc/openlist:/opt/openlist/data \
  -p 5244:5244 \
  -e UMASK=022 \
  --name="openlist" \
  xiguanle/openlist:latest
```

**方式二：使用默认用户 (1001)**

如果您希望使用容器内置的默认 `openlist` 用户 (UID 1001) 运行：

```bash
mkdir -p /etc/openlist
sudo chown -R 1001:1001 /etc/openlist
docker run -d --restart=unless-stopped \
  -v /etc/openlist:/opt/openlist/data \
  -p 5244:5244 \
  -e UMASK=022 \
  --name="openlist" \
  xiguanle/openlist:latest
```

*注：ClawCloud 同理使用 Lite 版本镜像。*

## 免责声明

1. 本项目仅供学习和交流使用，请勿用于商业用途。
2. 本项目所涉及的任何脚本、程序或资源，仅用于测试和研究目的。
3. 使用者应在下载后的24小时内删除相关文件。
4. 使用者需自行承担使用本项目可能产生的一切法律后果和风险，作者不承担任何责任。
5. 如果您不能接受本声明的任何条款，请立即停止使用本项目。
