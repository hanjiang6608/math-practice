# 🎯 快速开始（GitHub Pages）

## ✅ 你的专属链接

部署成功后，你的应用将可以通过以下链接访问：

```
https://hanjiang6608.github.io/math-practice/
```

---

## 🚀 一键部署命令

### 第1步：创建GitHub仓库
1. 访问：https://github.com/new
2. 仓库名称填写：**hanjiang6608**（使用此名称作为仓库名）
3. 选择 **Public**（必须公开）
4. 点击 **Create repository**

### 第2步：复制并执行以下命令

打开命令行（CMD/PowerShell/Terminal），执行：

```bash
# 进入项目文件夹
cd C:\Users\Administrator\Documents\opencode\math-practice-wechat

# 初始化Git仓库
git init

# 添加所有文件
git add .

# 提交文件
git commit -m "Initial commit"

# 连接到你的GitHub仓库
git remote add origin https://github.com/hanjiang6608/math-practice.git

# 推送到GitHub
git branch -M main
git push -u origin main
```

### 第3步：开启GitHub Pages
1. 访问：https://github.com/hanjiang6608/math-practice/settings/pages
2. Source选择：**Deploy from a branch**
3. Branch选择：**main** 和 **/(root)**
4. 点击 **Save**

### 第4步：等待并访问
等待1-2分钟，访问：
**https://hanjiang6608.github.io/math-practice/**

---

## 📱 微信中使用

1. 复制链接发送给微信好友或自己
2. 点击链接即可使用
3. 可以收藏到「我 → 收藏」方便下次使用

---

## 📝 功能说明

### 智能出题
- 自动分析你的错题类型
- 错误率高的题型会增加出题概率
- 三种难度可选

### 数据统计
- 实时显示正确率
- 保存最近100道练习记录
- 可视化错题分析图表

### 数据存储
- 所有数据保存在手机本地
- 不清理缓存数据不会丢失
- 换设备需要重新开始

---

## 🎨 界面预览

- 📊 **练习页**：显示题目、输入答案、虚拟键盘
- 📋 **记录页**：查看历史练习记录和统计
- 🔍 **分析页**：查看薄弱点和学习建议

---

## ⚡ 快速操作指南

| 操作 | 说明 |
|------|------|
| 开始练习 | 点击「开始练习」按钮 |
| 输入答案 | 点击数字键盘或使用手机键盘 |
| 提交答案 | 点击「确定」或按回车键 |
| 切换难度 | 在练习页点击简单/中等/困难 |
| 查看记录 | 点击底部「记录」标签 |
| 查看分析 | 点击底部「分析」标签 |
| 清空数据 | 在记录页点击「清空」按钮 |

---

## 🔄 更新代码

如果修改了代码，执行：

```bash
cd C:\Users\Administrator\Documents\opencode\math-practice-wechat
git add .
git commit -m "更新内容描述"
git push origin main
```

等待1-2分钟即可看到更新。

---

## ⚠️ 重要提示

1. **必须公开仓库**：GitHub Pages免费版要求仓库为Public
2. **HTTPS链接**：微信要求必须使用https://开头的链接
3. **数据本地化**：数据存储在浏览器，换设备会丢失
4. **国内访问**：GitHub Pages在国内访问可能较慢，如需更快速度建议使用腾讯云COS

---

## 🆘 遇到问题？

查看详细部署指南：**GITHUB_PAGES_DEPLOY.md**

GitHub Pages官方文档：https://docs.github.com/zh/pages

---

**祝使用愉快！** 🎉
