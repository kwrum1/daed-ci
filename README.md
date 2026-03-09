一个预构建 daed 的编译仓库。

## ImmortalWrt ipq60xx APK 云编译（仅插件包）

已添加 GitHub Actions 工作流：

- `.github/workflows/immortalwrt-ipq60xx-apk.yml`

功能：

- 支持手动触发，指定 `VIKINGYFY/immortalwrt` 的分支/标签/提交。
- 支持手动输入要编译的插件包（空格分隔），默认：`daed luci-app-daed`。
- 自动拉取 feeds 并生成 `ipq60xx` 目标配置。
- 打开 `CONFIG_USE_APK`，生成 OpenWrt 可用的 APK 包输出。
- **仅执行包编译与 `package/index`，不会构建固件镜像。**
- 包编译失败时自动回退到单线程重试，便于稳定构建与定位报错。
- 自动按日期+运行号发布到 GitHub Release：
  - 标签格式：`ipq60xx-apk-YYYYMMDD-<run_number>`
  - 发布名称：`ImmortalWrt ipq60xx APK YYYYMMDD #<run_number>`
- 构建完成后上传：
  - Actions 产物：`release-files/**`
  - Release 附件：`.apk` 与 `APKINDEX*`

你可以在仓库的 **Actions** 页面执行该工作流并下载 APK 包。
