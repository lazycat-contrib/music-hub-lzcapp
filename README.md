# music-hub-lzcapp

[Music Hub](https://github.com/io-aoleo/music-hub) 的懒猫微服 LPK 打包（镜像模式，LPK v2）。

- 包名：`community.lazycat.app.music-hub`
- 上游镜像：`docker.io/ioaoleo/music-hub`（官方镜像，注意 tag 无 v 前缀）
- 版本源：镜像 tag（`1.0.0` 三段式 semver）
- 发布目标：喵喵商店（私有/社区商店）

## 数据目录

- `/lzcapp/var/music` → 容器 `/music`：下载的音乐文件
- `/lzcapp/var/tasks` → 容器 `/data/tasks`：任务数据
- `/lzcapp/var/engine` → 容器 `/data/engine`：内嵌下载引擎数据

## 免密登录

首次打开需在页面创建管理员账号。三阶段联动：
request 捕获 setup/login 凭据 → response 2xx 持久化 → browser 自动填充。
