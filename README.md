一个预构建 daed 的编译仓库。

## ImmortalWrt ipq60xx APK 云编译

已添加 GitHub Actions 工作流：

- `.github/workflows/immortalwrt-ipq60xx-apk.yml`

功能：

- 支持手动触发，指定 `VIKINGYFY/immortalwrt` 的分支/标签/提交。
- 自动拉取 feeds 并生成 `ipq60xx` 目标配置。
- 打开 `CONFIG_USE_APK`，生成 OpenWrt 可用的 APK 包输出。
- 构建完成后上传：
  - `bin/targets/**`
  - `bin/packages/**`

你可以在仓库的 **Actions** 页面执行该工作流。
