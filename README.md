# 🗺️ 法意纵贯 · 文艺复兴之路 - 10日协同旅游行程网

这是一个专门为旅行团队/全家人出游打造的**单页面响应式法意10日游行程规划网站**。它不仅具备精美的界面和顺滑的细节体验，更支持**公网多人实时协同、离线存储、Excel/JSON导入导出以及时间线日程自由编辑**！

由于引入了免费公网高可用键值数据库缓存，本程序是**完全无服务（Serverless）设计**的，因此完美支持直接部署在 **GitHub Pages**, **Gitee Pages**, 或 **Netlify** 等完全免费的静态托管平台上，无需任何服务器。

---

## 🌟 核心功能亮点

* **📅 智能排期卡片**：只需选择第一天出发日期，后续所有日程的公历日期、星期几和酷炫角标都会自动推算并整齐展示。
* **🏨 高星名宿与航班呈现**：内置去程 MU569 直飞巴黎、回程 MU788 直飞上海的航班起降，包含精心挑选的巴黎美居、尼斯阿斯顿拉斯卡拉、佛罗伦萨巴廖尼等高星口碑酒店。
* **☁️ 公网多人协同 (重点)**：在侧边栏输入任意“通道协同码”（如 `fayi2026`）连入公网云端。一旦开启，网页会自动在后台同步多人的修改。
* **🔒 冲突防覆盖保护**：当您处于打字进行编辑时，自动同步程序将自我挂起，决不覆盖您辛苦码好的任何一个字！
* **🛠️ 极易编辑**：点击行程卡片右上角“修改日程”按钮，增删上午/下午/晚上活动，操作轻松丝滑。
* **📂 离线优先与备份**：离线状态下自动存储在浏览器 LocalStorage；支持一键生成 JSON 配置文件备份或发给朋友直接导入。

---

## 🚀 极速部署到 GitHub Pages (全免费)

由于本网站完全由静态 HTML/Tailwind CSS 构成，在 GitHub Pages 上运行是最合适且高逼格的选择。

以下是为您准备的 **3分钟极速部署指南**：

### 1. 初始化本地仓库并提交

在终端（或 VS Code 终端）中输入以下指令，将代码托管在本地：

```bash
# 初始化 Git
git init

# 切换为默认主分支 main
git checkout -b main

# 添加所有需要上线的文件
git add .

# 提交到本地版本库
git commit -m "feat: 初始化多人实时协作端旅游网站布局"
```

### 2. 在 GitHub 上新建一个 Repository (仓库)

1. 打开浏览器登录 [GitHub.com](https://github.com)（若无账号可免费注册）。
2. 在右上角点击 **`+`** ➔ 选择 **`New repository`**。
3. 填写仓库属性：
   * **Repository name**: `travel-itinerary-app` （或任意你心仪的英文名）
   * **Public/Private**: 选择 **`Public`** (公开仓库，GitHub Pages 仅免费对 Public 开放)。
   * **其他选项**: 保持默认，不要勾选 "Add a README file"、"Add .gitignore" 等（因为本地已经创建了）。
4. 点击最下方的绿色 **`Create repository`** 按钮。

### 3. 将本地代码推送到 GitHub

在创建成功后的 GitHub 网页上，复制指向该新建仓库的命令。通常格式如下，直接拷贝到您的终端里运行：

```bash
# 把关联的远程仓库地址（请将其换成你在 GitHub 网页上拿到的真实地址！）
git remote add origin https://github.com/【你的GitHub用户名】/travel-itinerary-app.git

# 推送代码到 GitHub
git push -u origin main
```

### 4. 开启 GitHub Pages 傻瓜式托管

1. 在你的 GitHub 仓库网页顶部，点击右侧的 ⚙️ **`Settings`** (设置)。
2. 在左侧导航栏的 "Code and automation" 下，点击 🌐 **`Pages`**。
3. 在 **Build and deployment** 下找到选单：
   * **Source**: 确保选择 `Deploy from a branch`。
   * **Branch**: 默认是 `None`，点击下拉菜单选择 **`main`**，右侧文件夹选择 **`/ (root)`**。
4. 点击旁边的 💾 **`Save`** 按钮。
5. 稍等 1-2 分钟，GitHub 会在页面顶部生成你对外界公开的专属行程网址：
   * 格式一般为：`https://【你的GitHub用户名】.github.io/travel-itinerary-app/index.html` 

---

## 👪 如何与家人分享并协同编辑？

全家人出门在机场或者酒店，怎么能同时编辑？

1. **直接分发带通道码的链接**：
   你可以复制已经关联好通道码的代码分发给家人：
   `https://【你的用户名】.github.io/travel-itinerary-app/index.html?code=fayi2026`
2. **扫码或点开即用**：
   全家人点开此链接并在各自的设备上刷新一下，系统就会立刻发现并连入 `fayi2026` 专属协同信道。
3. **快乐定制，互通有无**：
   爸爸在手机上给 Day 5 增加了吃冰淇淋的上午安排，存盘后妈妈在 Day 5 卡片上大约 8 秒后就会听到自动刷新的状态提示，立即展示出了冰淇淋图标签！

---

## 🛠️ 本地调试方案

若需在局域网段或脱网做调试：

```bash
# 启动本地服务运行环境
python3 server.py
```
然后用浏览器拉取 [http://localhost:8000/index.html](http://localhost:8000/index.html) 进行查看和调试即可。
