# 欲下番茄（修改中。。。。。。）


由于项目(https://github.com/zhongbai2333/Tomato-Novel-Downloader)不接受建议，于是我根据Zhongbai2333的项目Fork并修改

计划抛弃TUI和CLI，只支持Web UI并简化安装步骤。

## 我该如何使用？
服务器端只支持安装在安卓，Windows, Mac, Linux中，iPhone不支持。
客户端可以是任何可以上网的设备。安卓，iPhone，Windows, Mac, Linux都可以。iPad, iphone, android tablet,推荐使用google chrome浏览器。生成的ePub文件可以用任何支持ePub的阅读打开。

**手机端仅限安卓设备**
    先安装termux,可以在play store下载，如果找不到，寻找开源下载termux
    链接:(<https://github.com/termux/termux-app/releases>) 并安装，然后运行部署脚本：
    
    ```sh
    bash <(curl -sL https://raw.githubusercontent.com/yizhouhe/tdTomato/main/installer.sh)
    ``` 
   如果你希望在 TUI 中使用 `Ctrl+V` 从系统剪贴板粘贴，需要安装 Termux API：

   - 安装 App：Termux:API
   - 安装命令：'pkg install termux-api'
   - 验证：'termux-clipboard-get' 可正常输出内容

   安装完成后，推荐用 Web UI 启动（示例）：

   ```bash
   TOMATO_WEB_ADDR=0.0.0.0:18423 TOMATO_WEB_PASSWORD=你的密码 tomato-novel-downloader --server
   ```

   然后在浏览器打开：

   - 本机：'http://127.0.0.1:18423/'
   - 局域网其它设备：'http://<手机的局域网IP>:18423/'

**电脑端该如何运行？**

    Windows 双击运行`TomatoNovelDownloader-Win64-[当前版本号].exe

    Linux 和 MacOS 使用终端运行，可以使用一键部署脚本：

    ```sh
    bash <(curl -sL https://raw.githubusercontent.com/yizhouhe/tdTomato/main/installer.sh)
    ```



- 启动 Web UI：

    ```sh
    Tomato-Novel-Downloader.exe --server
    ```

- 监听地址（默认 `127.0.0.1:18423`）：

    通过环境变量修改监听地址，例如局域网访问：

    ```sh
    TOMATO_WEB_ADDR=0.0.0.0:18423
    ```

    IPv6 监听示例（注意 IPv6 需要方括号）：

    ```sh
    TOMATO_WEB_ADDR=[::]:18423
    ```

    同时监听多个地址（用逗号或分号分隔），例如同时监听 IPv4 + IPv6：

    ```sh
    TOMATO_WEB_ADDR=0.0.0.0:18423,[::]:18423
    ```

- 密码锁模式（防止陌生人使用）：

    ```sh
    Tomato-Novel-Downloader.exe --server --password 你的密码
    ```

    或者使用环境变量：

    ```sh
    TOMATO_WEB_PASSWORD=你的密码
    ```
   

**Web UI 提供的功能（纯 HTML，无需额外前端构建）：**

- 搜索书籍并创建下载任务
- 任务列表/进度刷新/取消任务
- 下载库按目录浏览（不再把所有文件递归平铺）
- 文件直接下载
- 文件夹一键打包为 zip 下载（保持目录结构，适配音频等“文件夹内包含文件夹”的情况）
- 配置页面：可在线修改部分下载输出相关配置（会写回 `config.yml`）

注意：Web UI 主要面向自建/局域网使用；如果要暴露到公网，建议放在反向代理/HTTPS 后面，并务必开启密码锁。

---


## 注意事项（必看）

由于使用的是api，所以未来不知道有哪一天突然失效，如果真的出现了，请立即在“Issues”页面中回复！

如果您在使用本程序的时候出现了下载章节失败的情况，也许并不是api失效了，可能是因为调用api人数过多，导致api暂时关闭，如果遇到了这种情况，请稍后再试，另外，您需要下载的小说api可能会因没有更新所以下载失败。

千万不要想着耍小聪明：“欸，我改一下线程数不就能快速下载了吗？”请打消这种念头！因为这样会加大服务器压力！！！

另外，在使用本程序时，请不要使用任何vpn或网络代理等一切影响网络正常使用的程序！

如果您也没有遇到以上的这种情况，请检查要下载的小说章节数量有多少，不建议大于1500章！(保守估计)

>划重点：切记！不能将此程序用于违法用途，例如将下载到的小说进行转载、给不良人员分享此程序使用等。本开发者严禁不支持这样做！！！并且请不要将api进行转载使用，除非您已经与开发者协商过，否则后果自负！下载到的小说仅供自行阅读，看完之后请立即删除文件，以免造成侵权，如果您还是偷尝禁果，需自行承担由此引发的任何法律责任和风险。程序的作者及项目贡献者不对因使用本程序所造成的任何损失、损害或法律后果负责！

## 免责声明

  本程序仅供 Rust 网络爬虫技术、网页数据处理及相关研究的学习用途。请勿将其用于任何违反法律法规或侵犯他人权益的活动。
  
  使用本程序的用户需自行承担由此引发的任何法律责任和风险。程序的作者及项目贡献者不对因使用本程序所造成的任何损失、损害或法律后果负责。
  
  在使用本程序之前，请确保您遵守适用的法律法规以及目标网站的使用政策。如有任何疑问或顾虑，请咨询专业法律顾问。

## 感谢

感谢用户选择此程序，如果喜欢可以加star，如果有什么对本程序的建议，请在“Issues”页面提出。您的喜欢就是我更新的最大动力❤️

项目前期 · 感谢原作者Zhongbai2333用Rust重写了项目

项目前期 · 感谢原作者Dimily的基础项目

项目前期 · 感谢来自Github用户@helloplhm-qwq的api！

项目前期 · 感谢来自QQ用户@终忆的api！

项目前期 · 感谢来自Github用户@jingluopro的api！！


End of readme for end user
==================================


## 构建模式（Cargo Features）

本项目提供两个互斥的 feature：`official-api` 与 `no-official-api`（两者不能同时启用）。

### 默认模式：official-api（默认启用）

- 构建（默认就会启用）：

```sh
cargo build --release
```

- 行为：
  - 搜索功能可用（TUI / Web UI / 老 CLI 的搜索入口）。
  - 段评（EPUB 段评页/资源抓取）可用（取决于配置项）。
  - 正文获取可通过配置在“官方/第三方”之间切换（`use_official_api`）。

### No-Official-API 模式：no-official-api（Issue #187）

- 构建：

```sh
# Linux/macOS
cp Cargo_no_official.toml Cargo.toml
cargo build --release

# Windows
copy /Y Cargo_no_official.toml Cargo.toml
cargo build --release
```

仓库根目录提供了 `Cargo_no_official.toml`，该文件**完全不引用** `tomato-novel-official-api` 路径依赖，适合无法获取该 crate 的用户直接使用。

- 行为差异（重点）：
  - **不依赖** `tomato-novel-official-api` crate，可在缺少 Official-API 环境时编译。
  - 目录与书本信息：使用网页解析（`FanqieWebNetwork`）。
  - **正文获取：强制第三方模式**（忽略/不使用 `use_official_api=true` 的官方分支）。
  - 搜索功能：不可用（会返回提示/报错）。
  - 段评：不可用（会被强制关闭）。

---
