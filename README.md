# YYeTsWeb
此项目是 https://github.com/tgbot-collection/YYeTsBot 网站 docker 部署方式的一个问题修复和冗余备份，用于在本地快速启动 YYeTsWeb 项目

## 原教程
https://github.com/tgbot-collection/YYeTsBot/blob/master/DEVELOPMENT.md#%E4%B8%80%E9%94%AE%E8%84%9A%E6%9C%AC

## 改动
* 修复 `docker-compose` 命令被弃用的问题
* 更新导入数据库时使用的 docker 名称 `yyets_mongo_1` -> `yyets-mongo-1`
* 为了方便部署到自己的服务器上，去掉了只能从 `127.0.0.1` 地址访问的限制
* 为了防止 `yyets.dmesg.app` 域名在未来的某一天无法打开，将数据库备份至本仓库

## 环境
* Linux for amd64，理论上支持 arm64 平台和 Windows 操作系统但是未测试本仓库的脚本在其他平台上的可用性（参考原教程）
* 需要如下软件包： `docker` `docker-compose` `curl`，为了方便使用这里给出在 CentOS 上安装 [docker](https://docs.docker.com/engine/install/centos/#install-using-the-repository)、[docker-compose](https://docs.docker.com/compose/install/linux/)的教程

## 使用
```bash
sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/Cnotech/YYeTsWeb/master/scripts/install.sh)"
```