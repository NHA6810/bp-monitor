## 项目概述
血压记录管理（bp-monitor）：一个纯前端单页应用，用于记录、分析和导出个人血压数据。部署在 GitHub Pages（https://nha6810.github.io/bp-monitor/）。

## 技术栈
- 纯 HTML + CSS + JavaScript 单文件应用（index.html）
- Chart.js 4.4.0（趋势图）
- SheetJS (xlsx) 0.18.5（Excel 导出）
- 百度 OCR API（血压计拍照识别）
- localStorage（本地数据持久化）
- GitHub API（数据同步）

## 目录结构
- `index.html` — 完整应用（HTML + CSS + JS 全部内联）
- `scripts/run.sh` — 预览启动脚本

## 关键入口 / 核心模块
- 数据记录：`renderList()`、`saveReading()`、`deleteReading()`
- 拍照识别：`handleImageCapture()`、`doOCR()`、`parseBPFromText()`
- 数据分析：`loadAnalysis()`、`generateExcelBlob()`
- 数据同步：`syncToGitHub()`、`syncFromGitHub()`
- 状态判断：`getStatus()` — 正常/正常高值/偏高

## 运行与预览
- 纯静态 HTML，无需构建步骤
- 预览：`bash scripts/run.sh`（serve -l 5000）
- 数据存储在浏览器 localStorage，首次加载从 data.json 读取初始数据

## 用户偏好与长期约束
- 单文件架构，所有改动集中在 index.html
- 血压单位：mmHg，脉搏单位：bpm
- 配色方案：暖色系（#F4735C 主色、#F5F0EB 背景）
