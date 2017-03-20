# Chrome升级清单

> 概述Electron中每次升级Chrome所需的步骤

除了更新任何Chrome / Node API更改的Electron代码之外,还有这些事情需要处理:
- 验证新版本的可用性 https://github.com/zcbenz/chromium-source-tarball/releases
- 更新 `electron/libchromiumcontent`存储库根目录下的 `VERSION`文件
- 更新 `script/update-clang.sh`里的 `CLANG_REVISION`,确保和 `libchromiumcontent/src/tools/clang/scripts/update.py`中使用的版本一致
- 更新 `vendor/node`到与新版Chrome版本中使用的v8版本相对应的Node版本. 有关更多详细信息，请参阅https://nodejs.org/en/download/releases 的Node中的v8版本
- 更新 `vendor/crashpad`
- 更新 `vendor/depot_tools`
- 更新  `libchromiumcontent`  为 `script/lib/config.py`中下载的SHA-1
- 在更改的 `electron/libchromiumcontent`打开一个pull请求
- 在更改的 `electron/brightray`打开一个pull请求
  - 包括 `vendor/libchromiumcontent` 子模块的升级
- 在更改的 `electron/electron`打开一个pull请求
  - 包括 `vendor/`中所需子模块的升级
- V验证调试生成成功:
  - macOS
  - 32-bit Windows
  - 64-bit Window
  - 32-bit Linux
  - 64-bit Linux
  - ARM Linux
- 验证版本构建成功:
  - macOS
  - 32-bit Windows
  - 64-bit Window
  - 32-bit Linux
  - 64-bit Linux
  - ARM Linux
- 验证测试通过:
  - macOS
  - 32-bit Windows
  - 64-bit Window
  - 32-bit Linux
  - 64-bit Linux
  - ARM Linux

## 链接

- [Chrome更新](https://www.chromium.org/developers/calendar)
