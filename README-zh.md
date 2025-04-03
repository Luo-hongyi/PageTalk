<h1 align="center">
  <strong>PageTalk - 你的网页 Gemini 助手 ✨</strong>
</h1>

<p align="center">
  <a href="https://github.com/jeanchristophe13v/PageTalk"> <!-- 如果有仓库链接，请替换 -->
    <img src="magic.png?raw=true" alt="Pagetalk 图标" title="Pagetalk 图标" width="250">
  </a>
</p>

#### [English/英文](README.md)

## 简介

Pagetalk 是一款浏览器插件，通过集成 Google Gemini API 来增强您的网页浏览体验。轻松总结页面、进行上下文对话，并管理自定义 AI 助手。

## 2.2.0 版本新特性 🎉

*   增加 LaTeX 支持！
*   增加 Mermaid 支持！（仍有一些 bug，会尽快修复）
*   增加助手设置导入/导出功能
*   增加当前聊天记录导出功能
*   增加中/英文语言支持
*   增加深色模式
*   再次优化 UI

## 主要特性

*   **网页交互:** 读取页面内容，提供对话上下文。
*   **Gemini API 集成:** 利用 Gemini 实现强大的语言功能。
*   **上下文聊天:** 与 AI 讨论当前网页内容。
*   **多助手系统:** 创建、自定义、切换并**导入/导出** AI 助手。
*   **模型选择:** 可选择多种 Gemini 模型。
*   **图片输入:** 上传或粘贴图片进行讨论。
*   **富文本渲染:** 支持 Markdown、代码高亮、**LaTeX** 公式和 **Mermaid** 图表。
*   **个性化设置:** 配置 API 密钥、**语言 (中/英)**、**主题 (浅色/深色)**。
*   **聊天导出:** 将对话保存为 Markdown 或纯文本文件。
*   **可调整面板:** 调整侧边栏宽度。

## 安装

**注意:** 需要在开发者模式下以“加载已解压的扩展程序”方式安装。

1.  **Edge:** 地址栏输入 `edge://extensions/` -> 启用“开发者模式” -> 点击“加载解压缩的扩展” -> 选择项目文件夹。
2.  **Chrome:** 地址栏输入 `chrome://extensions/` -> 启用“开发者模式” -> 点击“加载已解压的扩展程序” -> 选择项目文件夹。

## 使用说明

1.  **打开:** 点击 Pagetalk 图标或使用快捷键 (默认 `Alt+P`)。
2.  **聊天标签页:**
    *   选择模型/助手。
    *   提取页面内容（自动或手动），状态栏显示上下文长度。
    *   输入消息或粘贴/上传图片。
    *   发送消息（回车或按钮）。
    *   使用“总结一下”快捷操作。
    *   清除历史记录/上下文（垃圾桶图标）。
    *   鼠标悬停消息可复制/删除/重新生成。
    *   AI 回复中的 LaTeX (`$...$`, `$$...$$`) 或 Mermaid (```mermaid ... ```) 语法将自动渲染。点击 Mermaid 图表可缩放/平移查看。
3.  **设置标签页:** (包含通用、助手、模型子标签页)
    *   **通用:** 切换语言/主题，导出聊天记录。
    *   **助手:** 管理助手，导入/导出配置。
    *   **模型:** 设置 API 密钥，选择默认模型，开关自动提取。

## 项目结构

```
Pagetalk/
├── magic.png             # 图标
├── manifest.json         # 插件清单文件
├── README.md             # 英文说明
├── README-zh.md          # 中文说明
├── css/                  # 样式文件
│   ├── code-highlight.css
│   ├── content-panel.css
│   └── sidepanel.css
├── html/                 # HTML 文件
│   └── sidepanel.html
└── js/                   # JavaScript 逻辑
    ├── background.js     # Service Worker
    ├── content.js        # 内容脚本
    ├── markdown-renderer.js # Markdown 渲染逻辑
    ├── sidepanel.js      # 侧边栏 UI 核心逻辑
    ├── api.js            # Gemini API 交互逻辑
    ├── translations.js   # UI 字符串翻译
    └── lib/              # 第三方库
        ├── markdown-it.min.js
        ├── katex.min.js      # LaTeX 渲染
        ├── mermaid.min.js    # Mermaid 图表渲染
        ├── dayjs.min.js      # 日期时间库
        ├── panzoom.min.js    # Mermaid 缩放/平移库
        └── ...             # 其他库 (highlight.js 等)