# DL Debugger

一款轻量的 Chrome 扩展，帮你在浏览器里直接拦截 API 返回自定义数据、给请求注入自定义 Header。不用改代码，不用起 Mock 服务器，装上就能用。

### 👉 [立即下载 v2.0.0](https://github.com/evenjxr/DL-debugger-zip/releases/download/2.0.0/dist.zip)

> 下载 zip 解压后，打开 `chrome://extensions/` → 开启「开发者模式」→「加载已解压的扩展程序」→ 选择解压出的 `dist` 目录即可。

![主界面](productions/images/image1.png)

---

## 为什么需要它

前端开发经常遇到这些情况：后端接口还没写完，你需要假数据先跑起来；线上环境想验证某个接口在不同返回值下的表现，但你改不了后端；联调时需要给请求带上特定的 Token 或泳道标识。DL Debugger 就是用来解决这些问题的——打开 Popup 配好规则，刷新页面就生效。

---

## 核心功能

### 接口代理（Mock）

填写 API 路径（如 `/api/users`），选择 HTTP 方法，写好你想返回的 JSON，保存后这个接口的请求就会被拦截，浏览器直接拿到你定义的响应，请求不会真正发到后端。

![JSON 编辑器 — 编辑响应数据](productions/images/image2.png)

### 请求头注入

给某个 Host 下的所有请求自动添加 Header，比如 `access-token`、`x-shepherd-swimlane` 之类。每条 Header 规则独立开关，点击卡片即可编辑名称和值。

### 实时捕获

在 JSON 编辑器里点击「填充捕获」，插件会自动抓取当前页面对应路径的真实响应数据，一键填入编辑器。你可以在真实数据的基础上做修改，不用手动从 DevTools 里复制。

![捕获填充](productions/images/image5.png)

### 多 Host 管理

左侧面板列出所有 Host 配置，打开 Popup 时自动高亮当前页面匹配的站点。每个 Host 下独立维护「头信息」和「接口代理」两组规则，互不干扰。支持通配符（`*.example.com`）和带端口号的地址（`localhost:8888`）。

### 全局开关 & 导入导出

顶栏右侧的总开关一键暂停所有规则（配置不丢失）。导出按钮把全部配置存为 JSON 文件，导入按钮从 JSON 恢复——同 Host 自动覆盖，新 Host 自动新增。方便团队共享或跨设备迁移。

---

## 效果演示

以 Bing 搜索为例，配置 `/AS/Suggestions` 接口的 Mock 后，无论搜索框输入什么，联想词都会变成你自定义的内容：

| Mock 前 | Mock 后 |
|---------|---------|
| ![Mock 前](productions/images/image4.png) | ![Mock 后](productions/images/image8.png) |

请求头注入的效果可以在 DevTools Network 面板里看到，自定义 Header 已经被加到请求中：

![请求头注入验证](productions/images/image6.png)

---

## 安装

**方式一：直接用打包好的版本**

下载仓库里的 `productions/dist.zip`，解压即可，不需要装依赖、不需要构建。

**方式二：从源码构建**

```bash
git clone https://github.com/AYuWei/DevApiDegbber.git
cd DevApiDegbber
npm install
npm run build
```

然后打开 `chrome://extensions/`，开启「开发者模式」，点击「加载已解压的扩展程序」，选择项目下的 `dist` 目录。

---

## 使用方法

**添加站点** — 点击左下角「+ 添加 Host」，输入域名或 IP（如 `api.example.com`、`localhost:8888`）。

**配置接口代理** — 在「接口代理」Tab 下点击「+ 添加接口」，输入路径、选择方法，点击卡片打开 JSON 编辑器写返回数据。

**配置请求头** — 在「头信息」Tab 下点击「+ 添加头信息」，填写 Header 名称和值。

**开关控制** — 每条规则前面的复选框控制单条开关，左侧 Host 卡片上的 Toggle 控制整个站点的开关，顶栏的总开关控制全局。

---

## 开发

```bash
npm run dev          # 开发模式，监听文件变化自动构建
npm run build        # 标准构建
npm run build:prod   # 生产构建（压缩代码）
npm run deploy       # 构建 + 打包 zip 到 productions/
```

开发模式下不压缩代码并生成 sourcemap。保存文件后 Vite 自动重新构建，去 `chrome://extensions/` 点一下扩展的刷新按钮即可看到效果。

---

## 技术栈

React 18 + Vite 5，Chrome Manifest V3。请求头修改和接口拦截通过 `declarativeNetRequest` API 实现，配置数据持久化在 `chrome.storage.local`。

---

## 项目结构

```
src/
├── popup/                  # Popup 弹窗主界面
│   ├── App.jsx             # 入口：全局开关、导入导出、Host 路由
│   ├── components/
│   │   ├── HostList.jsx    # 左侧 Host 列表
│   │   └── RuleDetail.jsx  # 右侧规则详情（头信息 + 接口代理）
│   └── styles.css
├── background/             # Service Worker
│   ├── main.js             # 消息监听、规则分发
│   └── utils/              # DNR 规则生成（Header / Path）
├── shared/                 # 公共组件
│   ├── JsonEditor.jsx      # JSON 编辑器（视图模式 / 文本模式 / 格式化 / 捕获填充）
│   └── hooks.js            # 配置列表、单 Host 配置的自定义 Hook
└── utils/
    ├── chromeApi.js         # Chrome API 封装（存储、规则应用、标签页）
    └── tool.js              # 工具函数
```

## License

MIT
