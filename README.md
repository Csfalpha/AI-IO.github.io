# AI-IO ICRA 2026 论文展示网站

本项目基于 [MasterRacing](https://github.com/MasterDroneRacing/MasterRacing.github.io) 网站的设计风格创建。

## 设计参考

网站结构、CSS 样式、以及部分布局均参考 MasterRacing 项目，保持了相同的学术展示风格和响应式设计。

## 复制的资源文件

从 MasterRacing.github.io-main 复制了以下文件到本项目：

### CSS 文件
- `static/css/master.css` - MasterRacing 的样式文件

### JavaScript 文件
- `static/js/index.js` - 交互逻辑

### 图标文件
- `static/images/favicon.svg` - 网站图标（已创建）

## 项目结构

```
icra2026-website/
├── index.html                    # 主页面（完全复用 MasterRacing 结构）
├── README.md                     # 本文件
├── .github/workflows/
│   └── deploy.yml           # GitHub Actions 自动部署
└── static/
    ├── css/
    │   ├── index.css          # 本项目样式
    │   └── master.css         # MasterRacing 引用样式
    ├── images/
    │   └── favicon.svg     # 网站图标
    ├── js/
    │   └── index.js         # JavaScript 交互逻辑
    └── videos/              # 视频目录（待添加）
```

## 主要特点

- ✅ **Bulma CSS 框架** - 完全采用 MasterRacing 的样式系统
- ✅ **响应式设计** - 移动端、平板端、桌面端自适应
- ✅ **学术风格** - 包含标题、作者、单位、会议信息
- ✅ **三个链接按钮** - Paper、arXiv、Code（与 MasterRacing 一致）
- ✅ **Teaser 视频区** - 预留了视频展示区域
- ✅ **自动部署** - 配置了 GitHub Actions workflow

## 与参考网站的主要差异

### 内容差异
- **标题**: AI-IO: An Aerodynamics-Inspired Real-Time Inertial Odometry for Quadrotors
- **作者**: Jiahao Cui*、Feng Yu*、Linzuo Zhang、Yu Hu、Danping Zou†
- **单位**: Shanghai Jiao Tong University
- **会议**: ICRA 2026（而非 RAL 2025）
- **摘要**: 完整替换为 AI-IO 论文摘要

### 技术栈
- **Bulma CSS 0.9.4** - CDN 链接
- **Font Awesome 6.4.0** - 图标库
- **jQuery 3.5.1** - DOM 操作
- **Google Fonts** - Google Sans、Noto Sans

## 快速开始

### 1. 复制 PDF 文件

```bash
cp /home/csf/.openclaw/media/inbound/AI-IO---f6a448e7-6eb5-4310-80c9-01a0c8f9ae52.pdf \
  /home/csf/.openclaw/workspace/icra2026-website/static/AI-IO.pdf
```

### 2. 创建 GitHub 仓库并推送

```bash
cd /home/csf/.openclaw/workspace/icra2026-website

# 初始化 Git 仓库
git init
git add .
git commit -m "Initial commit: AI-IO ICRA 2026 website (based on MasterRacing design)"

# 创建 GitHub 仓库（替换 YOUR_USERNAME 为你的 GitHub 用户名）
gh repo create icra2026-website --public \
  --description "ICRA 2026 AI-IO Paper Website" \
  --source=./

# 添加远程仓库并推送
git remote add origin https://github.com/YOUR_USERNAME/icra2026-website.git
git branch -M main
git push -u origin main
```

### 3. 启用 GitHub Pages

#### 方法一：通过 GitHub 网页界面（推荐）

1. 打开仓库页面：`https://github.com/YOUR_USERNAME/icra2026-website`
2. 进入 **Settings** → **Pages**
3. 在 **Build and deployment** 下选择：
   - **Source**: Deploy from a branch
   - **Branch**: `main`
4. 点击 **Save**

等待 1-2 分钟后，网站将部署在：
`https://YOUR_USERNAME.github.io/icra2026-website/`

#### 方法二：通过 GitHub Actions（自动化）

已配置 `.github/workflows/deploy.yml`，会在每次推送到 `main` 分支时自动部署。

### 4. 本地预览

使用简单的 HTTP 服务器预览：

```bash
cd /home/csf/.openclaw/workspace/icra2026-website
python -m http.server 8000
```

然后在浏览器打开：`http://localhost:8000`

## 添加演示视频

如果你有演示视频，按以下步骤添加：

1. 将视频重命名为 `demo.mp4`
2. 放到 `static/videos/` 目录：
```bash
mkdir -p static/videos
cp 你的视频.mp4 static/videos/demo.mp4
```
3. 在 `index.html` 中取消注释视频部分（找到第 94 行）

## 自定义修改

### 修改作者信息

编辑 `index.html` 中的作者区块（第 26-48 行）。

### 修改摘要

编辑 `index.html` 中的 Abstract 部分（第 94-135 行）。

### 修改配色

如果要调整网站配色，可以：
1. 编辑 `static/css/index.css` - 主样式文件
2. 引用 `static/css/master.css` - MasterRacing 的样式

## 注意事项

1. **PDF 文件**：需要手动复制到 `static/AI-IO.pdf`
2. **GitHub 用户名**：替换 `YOUR_USERNAME` 为你的实际 GitHub 用户名
3. **方法图片**：如需添加方法介绍图，将图片放入 `static/images/` 目录并在 `index.html` 中引用
4. **响应式设计**：已完全采用 MasterRacing 的响应式布局

## 技术栈

- **HTML5** - 语义化标签
- **Bulma CSS** - 响应式框架（CDN）
- **Font Awesome** - 图标库（CDN）
- **Google Fonts** - Google Sans、Noto Sans

## 许可证

MIT License - 可自由使用和修改

## 致谢

网站设计风格参考了 [MasterRacing](https://github.com/MasterDroneRacing/MasterRacing.github.io) 项目。

## 联系方式

如有问题，请联系：[你的邮箱]
或提交 Issue：https://github.com/SJTU-ViSYS-team/AI-IO/issues
