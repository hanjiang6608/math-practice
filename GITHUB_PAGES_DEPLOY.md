# 🚀 GitHub Pages 部署指南

## 📋 部署前准备

你的GitHub用户名：**hanjiang6608**

部署后将获得链接：**https://hanjiang6608.github.io/math-practice/**

## 📝 部署步骤

### 步骤1：创建GitHub仓库

1. 访问 https://github.com/new
2. 填写仓库信息：
   - **Repository name**: `math-practice` （必须完全一致）
   - **Description**: 小学三年级数学练习 - 微信H5应用
   - **Public**: 选中（必须公开才能使用GitHub Pages）
   - **Add a README file**: 不勾选
   - **Add .gitignore**: 不勾选
   - **Choose a license**: 不勾选

3. 点击 **Create repository**

### 步骤2：上传代码

#### 方法一：使用Git命令行

```bash
# 1. 打开命令行，进入项目文件夹
cd math-practice-wechat

# 2. 初始化Git仓库
git init

# 3. 添加文件
git add index.html README.md

# 4. 提交
git commit -m "Initial commit: 小学三年级数学练习应用"

# 5. 添加远程仓库（替换为你的用户名）
git remote add origin https://github.com/hanjiang6608/math-practice.git

# 6. 推送代码
git branch -M main
git push -u origin main
```

#### 方法二：使用GitHub Desktop（推荐新手）

1. 下载并安装 GitHub Desktop: https://desktop.github.com
2. 登录你的GitHub账号
3. 选择 File → Add local repository
4. 选择 `math-practice-wechat` 文件夹
5. 填写提交信息，点击 "Commit to main"
6. 点击 "Publish repository"
7. 确认仓库名称为 `math-practice`，点击 "Publish Repository"

#### 方法三：直接网页上传

1. 在GitHub仓库页面，点击 "Add file" → "Upload files"
2. 拖拽 `index.html` 到上传区域
3. 填写提交信息："Add index.html"
4. 点击 "Commit changes"

### 步骤3：开启GitHub Pages

1. 在你的仓库页面，点击 **Settings**（设置）标签
2. 左侧菜单找到并点击 **Pages**
3. 在 "Build and deployment" 部分：
   - **Source**: 选择 "Deploy from a branch"
   - **Branch**: 选择 "main" 和 "/ (root)"
4. 点击 **Save**

### 步骤4：等待部署完成

1. 页面会显示："Your site is ready to be published at https://hanjiang6608.github.io/math-practice/"
2. 等待 1-2 分钟
3. 刷新页面，看到 "Your site is live at https://hanjiang6608.github.io/math-practice/" 即部署成功

## 🔗 访问链接

部署成功后，你可以通过以下链接访问：

```
https://hanjiang6608.github.io/math-practice/
```

## 📱 在微信中使用

1. **直接发送链接**
   - 在微信聊天中发送：`https://hanjiang6608.github.io/math-practice/`
   - 点击链接即可打开

2. **收藏到微信**
   - 打开链接后，点击右上角「···」
   - 选择「收藏」
   - 以后在「我 → 收藏」中快速访问

3. **添加到浮窗**
   - 打开链接后，点击右上角「···」
   - 选择「浮窗」
   - 可在聊天界面右侧快速打开

4. **生成二维码**
   - 使用任意二维码生成工具
   - 输入链接生成二维码
   - 扫描即可访问

## 🔄 更新代码

如果后续需要修改代码：

```bash
# 1. 修改 index.html 文件

# 2. 提交更改
git add index.html
git commit -m "更新：xxx功能"

# 3. 推送到GitHub
git push origin main

# 4. 等待1-2分钟自动部署
```

## 🎨 自定义配置

### 修改页面标题
编辑 `index.html` 第7行：
```html
<title>你的自定义标题</title>
```

### 修改分享信息
编辑 `index.html` 第11-13行：
```html
<meta property="og:title" content="分享标题">
<meta property="og:description" content="分享描述">
<meta property="og:image" content="分享图片URL">
```

### 绑定自定义域名（可选）

如果你想用自己的域名（如 `math.yourdomain.com`）：

1. 在仓库根目录创建 `CNAME` 文件
2. 文件内容为你的域名：`math.yourdomain.com`
3. 在你的域名DNS设置中添加 CNAME 记录：
   - 主机记录：`math`
   - 记录值：`hanjiang6608.github.io`
4. 等待DNS生效（通常几分钟到几小时）

## ⚠️ 注意事项

1. **仓库必须是Public**
   - GitHub Pages免费版要求仓库公开
   - 私有仓库需要GitHub Pro才能使用Pages

2. **路径问题**
   - 确保所有资源路径使用相对路径 `./` 或绝对路径 `/math-practice/`
   - 已设置 `<base href="https://hanjiang6608.github.io/math-practice/">`

3. **HTTPS**
   - GitHub Pages自动提供HTTPS
   - 微信要求必须使用HTTPS链接

4. **访问速度**
   - GitHub Pages在国内访问可能较慢
   - 如需更快访问，建议使用 Vercel 或腾讯云COS

5. **缓存问题**
   - 更新后可能需要清除浏览器缓存才能看到最新版本
   - 微信内置浏览器缓存较严重，可尝试：
     - 删除聊天记录中的链接重新打开
     - 在微信设置中清理缓存

## 🐛 常见问题

### Q1: 页面404错误？
**解决**：
- 检查仓库名称是否为 `math-practice`
- 确认GitHub Pages设置中Branch选择了main
- 等待1-2分钟后刷新

### Q2: 样式错乱？
**解决**：
- 检查CSS路径是否正确
- 确保使用了 `<base>` 标签
- 清除浏览器缓存

### Q3: 微信打不开？
**解决**：
- 确保链接以 `https://` 开头
- 检查GitHub Pages是否部署成功
- 尝试在普通浏览器中打开测试

### Q4: 数据丢失？
**解决**：
- 数据存储在浏览器LocalStorage中
- 换设备或清理缓存会丢失数据
- 建议定期截图保存重要数据

### Q5: 如何添加多个页面？
**解决**：
- 创建新的HTML文件（如 about.html）
- 链接使用相对路径：`<a href="about.html">`
- 推送后通过 `https://hanjiang6608.github.io/math-practice/about.html` 访问

## 📊 部署状态检查

在GitHub仓库页面：
- 点击 **Actions** 标签
- 查看最近的工作流运行状态
- 绿色✓表示部署成功
- 红色✗表示部署失败，点击查看错误信息

## 🎯 下一步建议

1. **测试所有功能**
   - 练习功能
   - 历史记录
   - 错题分析
   - 数据持久化

2. **分享给朋友**
   - 发送链接给需要的家长
   - 收集反馈意见
   - 持续改进

3. **考虑迁移**
   - 如果国内访问慢，考虑迁移到：
     - Vercel（https://vercel.com）
     - 腾讯云COS
     - 阿里云OSS

## 📞 技术支持

GitHub Pages文档：https://docs.github.com/zh/pages

---

**祝你部署顺利！** 🎉
