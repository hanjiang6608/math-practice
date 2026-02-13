# 🚀 快速部署指南

本文档帮助你在5分钟内将数学练习应用部署到线上，供微信访问。

## 方案一：Vercel部署（推荐，免费且简单）

### 步骤：

1. **注册账号**
   - 访问 https://vercel.com
   - 使用 GitHub / GitLab / Bitbucket 账号登录

2. **导入项目**
   - 点击 "Add New Project"
   - 选择 "Import Git Repository"
   - 如果代码在GitHub上，直接选择仓库
   - 如果代码在本地，先上传到GitHub

3. **部署配置**
   - Framework Preset: 选择 "Other"
   - Build Command: 留空（无需构建）
   - Output Directory: 留空（使用根目录）

4. **一键部署**
   - 点击 "Deploy" 按钮
   - 等待1-2分钟
   - 获得链接：`https://项目名-用户名.vercel.app`

5. **访问测试**
   - 在微信中打开链接
   - 测试各项功能

✅ **优点**：免费、全球CDN、自动HTTPS、支持自定义域名

---

## 方案二：Netlify部署（免费且简单）

### 步骤：

1. **访问网站**
   - 打开 https://www.netlify.com
   - 注册或登录账号

2. **拖拽部署**
   - 在文件夹中选中 `index.html`
   - 直接拖拽到Netlify网页的部署区域
   - 自动完成部署

3. **获得链接**
   - 自动生成随机链接
   - 示例：`https://brave-pasteur-123456.netlify.app`

4. **自定义域名（可选）**
   - 在Site settings中设置
   - 可以使用自己的域名

✅ **优点**：无需Git、拖拽即可部署、支持表单功能

---

## 方案三：腾讯云COS部署（国内访问快）

### 步骤：

1. **购买COS服务**
   - 访问 https://console.cloud.tencent.com/cos
   - 注册腾讯云账号
   - 创建存储桶（选择「公有读私有写」）

2. **开启静态网站**
   - 进入存储桶详情
   - 点击「基础配置」-「静态网站」
   - 开启静态网站功能
   - 索引文档填写：`index.html`
   - 错误文档填写：`index.html`

3. **上传文件**
   - 进入「文件列表」
   - 点击「上传文件」
   - 选择 `index.html` 上传

4. **获取链接**
   - 静态网站URL示例：
     `https://bucket-name.cos-website.ap-guangzhou.myqcloud.com`

5. **配置CDN（可选）**
   - 开启CDN加速
   - 绑定自定义域名
   - 配置HTTPS证书

✅ **优点**：国内访问快、支持HTTPS、可绑定自定义域名

---

## 方案四：GitHub Pages部署（免费）

### 步骤：

1. **创建GitHub仓库**
   - 登录 https://github.com
   - 新建仓库，命名为 `math-practice`

2. **上传代码**
   ```bash
   # 本地操作
   git init
   git add index.html README.md
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/你的用户名/math-practice.git
   git push -u origin main
   ```

3. **开启GitHub Pages**
   - 进入仓库 Settings
   - 左侧选择 Pages
   - Source 选择 "Deploy from a branch"
   - Branch 选择 "main" 和 "/ (root)"
   - 点击 Save

4. **等待部署**
   - 等待1-2分钟
   - 访问：`https://你的用户名.github.io/math-practice`

✅ **优点**：完全免费、与Git集成、支持自定义域名

⚠️ **注意**：国内访问可能较慢

---

## 方案五：阿里云OSS部署

### 步骤：

1. **创建OSS Bucket**
   - 登录 https://oss.console.aliyun.com
   - 创建Bucket（选择「公共读」）

2. **开启静态网站托管**
   - 进入Bucket
   - 点击「基础设置」-「静态页面」
   - 开启静态页面
   - 默认首页：`index.html`
   - 默认404页：`index.html`

3. **上传文件**
   - 进入「文件管理」
   - 上传 `index.html`

4. **获取访问地址**
   - 静态页面访问地址示例：
     `http://bucket-name.oss-cn-hangzhou.aliyuncs.com`

✅ **优点**：国内访问快、稳定可靠、价格便宜

---

## 方案六：自有服务器部署

### Nginx配置示例：

```nginx
server {
    listen 80;
    server_name math.yourdomain.com;
    
    # 重定向到HTTPS
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name math.yourdomain.com;
    
    # SSL证书配置
    ssl_certificate /path/to/cert.pem;
    ssl_certificate_key /path/to/key.pem;
    
    root /var/www/math-practice;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
    
    # 缓存静态资源
    location ~* \.(html|js|css)$ {
        expires 1h;
        add_header Cache-Control "public, immutable";
    }
}
```

### Apache配置示例：

```apache
<VirtualHost *:80>
    ServerName math.yourdomain.com
    DocumentRoot /var/www/math-practice
    
    <Directory /var/www/math-practice>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
    
    # 重定向到HTTPS
    RewriteEngine On
    RewriteCond %{HTTPS} off
    RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</VirtualHost>
```

---

## 🔗 微信访问链接格式

部署成功后，你会获得类似以下格式的链接：

```
https://math-practice.vercel.app
https://math-practice.netlify.app
https://bucket-name.cos-website.ap-guangzhou.myqcloud.com
https://你的用户名.github.io/math-practice
https://math.yourdomain.com
```

**在微信中使用：**
1. 直接发送链接到聊天窗口
2. 点击链接即可打开
3. 可以收藏到微信收藏夹
4. 可以生成二维码分享

---

## 📱 微信分享配置（进阶）

如果想要更好的微信分享体验（自定义标题、描述、图片），需要：

### 1. 注册微信公众号
- 订阅号或服务号都可以
- 完成微信认证

### 2. 配置JS接口安全域名
- 登录公众号后台
- 设置与开发 → 公众号设置 → 功能设置
- 配置JS接口安全域名（填写你的H5域名）

### 3. 配置IP白名单
- 设置与开发 → 基本配置
- 配置服务器IP白名单

### 4. 使用微信JS-SDK
在你的H5页面中添加：

```html
<script src="https://res.wx.qq.com/open/js/jweixin-1.6.0.js"></script>
<script>
// 需要后端接口获取签名
fetch('/api/wechat-signature?url=' + encodeURIComponent(location.href.split('#')[0]))
  .then(res => res.json())
  .then(config => {
    wx.config({
      debug: false,
      appId: config.appId,
      timestamp: config.timestamp,
      nonceStr: config.nonceStr,
      signature: config.signature,
      jsApiList: ['updateAppMessageShareData', 'updateTimelineShareData']
    });
    
    wx.ready(function() {
      // 自定义分享内容
      wx.updateAppMessageShareData({
        title: '小学三年级数学练习',
        desc: '智能出题，错题分析，让数学学习更高效！',
        link: location.href,
        imgUrl: 'https://your-domain.com/share-icon.png',
        success: function() {
          console.log('分享设置成功');
        }
      });
    });
  });
</script>
```

⚠️ **注意**：这需要后端支持生成微信签名，如果只是个人使用，可以跳过此步骤。

---

## ✅ 部署检查清单

- [ ] H5页面可以正常访问
- [ ] 页面加载速度可接受
- [ ] 所有功能测试通过
- [ ] 数据可以正常保存
- [ ] 微信中可以正常打开
- [ ] 分享功能可用（基础版）
- [ ] 配置了HTTPS（微信要求）

---

## 🆘 常见问题

### Q1: 微信打不开链接？
**解决**：确保使用 `https://` 开头的链接，微信要求安全链接。

### Q2: 页面加载慢？
**解决**：
- 使用国内CDN（腾讯云COS、阿里云OSS）
- 开启Gzip压缩
- 配置浏览器缓存

### Q3: 数据丢失？
**解决**：
- 不要清理浏览器缓存
- 定期截图保存重要数据
- 考虑增加数据导出功能

### Q4: 如何绑定自定义域名？
**解决**：
- Vercel/Netlify：在控制台添加自定义域名
- COS/OSS：在控制台配置自定义域名和CDN
- 服务器：配置Nginx/Apache虚拟主机

---

## 💡 推荐方案总结

| 方案 | 难度 | 费用 | 国内速度 | 推荐指数 |
|------|------|------|----------|----------|
| Vercel | ⭐ | 免费 | ⭐⭐ | ⭐⭐⭐⭐ |
| Netlify | ⭐ | 免费 | ⭐⭐ | ⭐⭐⭐⭐ |
| 腾讯云COS | ⭐⭐ | 极低 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| GitHub Pages | ⭐ | 免费 | ⭐⭐ | ⭐⭐⭐ |
| 阿里云OSS | ⭐⭐ | 极低 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| 自有服务器 | ⭐⭐⭐ | 有 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |

**最推荐**：腾讯云COS 或 阿里云OSS，国内访问快且稳定。

---

**祝你部署顺利！** 🎉
