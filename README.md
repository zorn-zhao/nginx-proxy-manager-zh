
[Original English README](https://github.com/xiaoxinpro/nginx-proxy-manager-zh/blob/develop-zh/README-en.md)

<p align="center">
    <img src="https://nginxproxymanager.com/github.png">
    <br>
</p>

本项目是基于 [NginxProxyManager/nginx-proxy-manager](https://github.com/NginxProxyManager/nginx-proxy-manager) 翻译的中文版本，该项目属于一个预构建的docker映像，它可以让你轻松地部署到你的网站上运行，包括免费的SSL，而不需要知道太多关于 Nginx 或 Let's Encrypt 的信息。

![](http://image.xiaoxin.pro/2022/05/16/75687b5bfffbe.png)

## 快速部署

### 1. 环境部署

安装Docker和Docker-compose

- [Docker官方安装文档（英文）](https://docs.docker.com/install/)
- [Docker-Compose官方安装文档（英文）](https://docs.docker.com/compose/install/)
- **[Docker和Docker-compose安装文档（中文）](https://blog.csdn.net/zhangzejin3883/article/details/124778945)**

### 2. 创建YAML文件

创建一个 `docker-compose.yml` 文件:

```yml
version: '3'
services:
  app:
    image: 'chishin/nginx-proxy-manager-zh:release'
    restart: always
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```

This is the bare minimum configuration required. See the [documentation](https://nginxproxymanager.com/setup/) for more.

3. Bring up your stack by running

```bash
docker-compose up -d

# If using docker-compose-plugin
docker compose up -d

```

4. Log in to the Admin UI

When your docker container is running, connect to it on port `81` for the admin interface.
Sometimes this can take a little bit because of the entropy of keys.

[http://127.0.0.1:81](http://127.0.0.1:81)

Default Admin User:
```
Email:    admin@example.com
Password: changeme
```

Immediately after logging in with this default user you will be asked to modify your details and change your password.


## Contributing

All are welcome to create pull requests for this project, against the `develop` branch. Official releases are created from the `master` branch.

CI is used in this project. All PR's must pass before being considered. After passing,
docker builds for PR's are available on dockerhub for manual verifications.

Documentation within the `develop` branch is available for preview at
[https://develop.nginxproxymanager.com](https://develop.nginxproxymanager.com)


### Contributors

Special thanks to [all of our contributors](https://github.com/NginxProxyManager/nginx-proxy-manager/graphs/contributors).


## Getting Support

1. [Found a bug?](https://github.com/NginxProxyManager/nginx-proxy-manager/issues)
2. [Discussions](https://github.com/NginxProxyManager/nginx-proxy-manager/discussions)
3. [Reddit](https://reddit.com/r/nginxproxymanager)
