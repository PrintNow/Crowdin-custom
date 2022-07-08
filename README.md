# Crowdin

Crowdin CLI 镜像中，中包含 `git` 命令

GitHub 仓库地址：https://github.com/PrintNow/Crowdin-custom

## 背景

其实这个 Dockerfile 很简单，但由于项目需要，需要在 Crowdin 容器中使用 git 命令，所以想到如此对策

## 构建

- `-t crowdin:having-git` 指定构建镜像 tag *crowdin:having-git*
- `--network host` 使用宿主机网络
- `-f Dockerfile` 指定使用 *Dockerfile*

```shell
docker build -t crowdin:having-git --network host -f Dockerfile .
```

---

**如果你懒得构建，你可以使用已经构建好的镜像：**

Docker hub：[https://hub.docker.com/r/shine09/crowdin](https://hub.docker.com/r/shine09/crowdin)

```shell
docker pull shine09/crowdin:latest-having-git
docker run -it --rm shine09/crowdin:latest-having-git
```
