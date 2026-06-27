# 走遍美国学习版

> 《走遍美国》(Family Album U.S.A.) 英语学习版：26 集完整台词、逐句中文翻译、音频播放、全局搜索，纯前端无后端，开箱即用。

---
## ⚠️ 版权声明与免责说明

如原作者或出版社认为本项目侵犯了相关权益，请通过 GitHub Issues 联系，本人将立即删除相关内容。

---


## 功能特性

- **26 集 / 78 幕 / 6000+ 句台词**：完整覆盖《走遍美国》全剧集
- **逐句中文翻译**：英文与中文对照显示，可一键切换显隐
- **播放速度控制**：0.75× / 1× / 1.25× / 1.5× 四档可调
- **全局搜索**：跨 26 集搜索英文台词、中文翻译或集名，点击跳转（`Ctrl/Cmd + K` 唤起）
- **响应式设计**：桌面双栏、手机底部导航栏
- **纯静态部署**：无需后端，可直接托管到 GitHub Pages

---

## 在线预览

本项目可直接部署到 GitHub Pages，无需后端服务器：

**[👉 在线演示](https://shaozhengmao.github.io/family-album-usa-studied/)**

> 部署方式见下方「GitHub Pages 部署」章节。推送 `main` 分支后，仓库自带的 GitHub Actions workflow 会自动部署。

---

## 项目结构

```
family-album-usa-studied/
├── audio-acts/          # 78 个独立音频文件（每幕一个 mp3）
│   ├── e01_a1.mp3
│   ├── e01_a2.mp3
│   └── ... (e01 ~ e26，每集 3 个)
├── episodes.json        # 剧集数据（英文基于原版，中文翻译原创）
├── index.html           # 单页应用（完全原创代码）
├── .nojekyll            # 禁用 GitHub Pages 的 Jekyll 处理
├── .github/workflows/   # 自动部署到 GitHub Pages 的 workflow
└── README.md            # 本文件
```

### 数据格式

```json
{
  "episodes": [{
    "id": 1,
    "title": "46 Linden Street",
    "titleCn": "林登大街46号",
    "summary": "剧情简介...",
    "acts": [{
      "label": "Act I",
      "audio": "audio-acts/e01_a1.mp3",
      "hasAudio": true,
      "lineCount": 86,
      "lines": [{
        "t": 34.18,
        "en": "Excuse me. My name is Richard Stewart.",
        "cn": "打扰一下，我叫 Richard Stewart。"
      }]
    }]
  }]
}
```

**音频播放说明**：
- 每幕使用独立的 MP3 文件（`audio-acts/e{集数}_a{幕数}.mp3`）
- 台词时间戳 `t` 是相对该幕音频起始时间的偏移量（秒）

---

## 本地使用

### 方式一：直接打开（基础功能）

用浏览器直接打开 `index.html` 文件即可查看，但部分浏览器会因安全策略拦截 `fetch('episodes.json')`，**推荐使用方式二**。

### 方式二：本地服务器（推荐）

```bash
# Python 3
python3 -m http.server 8080

# Node.js
npx serve .

# 然后访问 http://localhost:8080
```

---

## GitHub Pages 部署

本项目**纯静态**，可直接部署到 GitHub Pages，**完全免费**。

### 自动部署（推荐）

仓库已包含 `.github/workflows/deploy.yml`，推送 `main` 分支会自动部署：

1. Fork 本仓库到你自己的 GitHub 账号
2. 进入仓库 → **Settings** → **Pages**
3. **Source** 选择 **GitHub Actions**
4. 推送代码到 `main` 分支，等待 Actions 跑完即可访问：
   `https://你的用户名.github.io/family-album-usa-studied/`

---

## 键盘快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl/Cmd + K` | 打开 / 关闭搜索 |
| `Esc` | 关闭搜索弹窗 |

---

## 浏览器支持

- Chrome / Edge / Firefox / Safari 最新版
- 支持移动端浏览（手机、平板自适应）

### 移动端特性

- 底部导航栏：首页、搜索、主题切换、翻译切换
- 自适应字体：根据屏幕宽度自动调整文字大小
- 触控优化：按钮和台词区域适合手指点击

---

## 许可证

MIT

> 本项目仅供英语学习交流使用，不得用于商业用途。
