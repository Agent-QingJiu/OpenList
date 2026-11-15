# OpenList 群晖套件

这是为群晖 DSM 6.2.3（x86_64 / bromolow）制作的 OpenList 安装套件。

## 适用环境

- 设备平台：DS3615xs / `synology_bromolow_3615xs`
- DSM 版本：`6.2.3-25426`
- 套件架构：`bromolow`（x86_64）
- 上游项目：[OpenList 官方仓库](https://github.com/OpenListTeam/OpenList)
- 自动构建：GitHub Actions

## 下载与安装

1. 打开本项目的 [Releases 发布页面](https://github.com/QiStore/OpenList/releases)。
2. 下载最新版本中的 `.spk` 安装包。
3. 在群晖 DSM 的「套件中心」中选择「手动安装」，上传 SPK 文件并按提示完成安装。

## 自动更新与构建

本项目会定期检查 OpenList 官方仓库是否发布了新的正式版本。发现尚未打包的新版本后，会自动启动群晖套件构建流程。

构建成功后，系统会自动创建 GitHub Release，并将 SPK 安装包作为附件上传。构建失败时不会发布安装包。

也可以在本项目的 **Actions → Build OpenList SPK (DSM 6.2.3)** 页面手动启动构建，并指定 OpenList 上游分支、标签或提交。

## 套件说明

- 套件由群晖「套件中心」负责启动、停止和管理。
- 默认 Web 访问端口为 **5244**。
- OpenList 的配置、数据库、索引、临时文件和日志保存在群晖套件变量目录中。
- 覆盖升级会更新应用程序文件，并保留套件变量目录中的数据。
- 卸载脚本会停止服务，不会主动删除套件变量目录中的数据。

## 兼容性说明

当前构建目标为 DSM 6.2.3、bromolow x86_64 平台。GitHub Actions 构建成功代表程序编译和 SPK 归档检查通过；升级或首次安装后，仍建议在实际设备上确认服务启动、访问及数据保留情况。

## 许可证

OpenList 上游项目采用 AGPL-3.0 许可证。相关许可证文件会随套件一同打包。
