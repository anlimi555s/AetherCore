# 起源框架 mod 发布仓库

本仓库是"起源管理器"游戏内联网更新的数据源, 由 _build-release.js 生成维护, 不要手工改 versions.json。

## 结构

- versions.json      更新清单(管理器读取)
- *.zip              各 mod 安装包(文件名带版本号)
- *.zip.partN        超 20MB 的包按字节切成的分卷(jsDelivr 单文件上限),
                     管理器自动下载全部分卷拼接还原; 手动安装请到 Releases 页下载完整包

## 发布新版本

1. 本地打好 mod zip
2. node date/_tools/_build-release.js <zip路径> --changes "更新说明"
3. 把 release/ 目录全部内容推送到本仓库根目录(大文件用 git push, 网页上传限 25MB)
4. (可选)在 Releases 页另挂完整 zip 供手动下载
5. jsDelivr 缓存约 5 分钟后全球可达; 改过的文件可访问 purge.jsdelivr.net 同路径立即刷新

## 玩家侧

游戏内侧栏"mod管理"入口, 更新页签一键检查与安装; 或到 Releases 页手动下载 zip 后经 Mod Loader 管理器安装。
