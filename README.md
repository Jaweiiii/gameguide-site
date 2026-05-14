# 游戏攻略站 - GameGuide Site

基于 Hexo + Fluid 主题搭建的游戏攻略网站，专注 Steam 单机和主机游戏攻略。

## 🎮 网站特色

- **Hexo 静态生成** - 速度快，SEO 友好
- **Fluid 主题** - 中文生态最好的 Hexo 主题，支持暗黑模式
- **广告位预留** - 百度联盟/Google AdSense 广告位已就绪
- **搜索功能** - 本地全文搜索
- **SEO 优化** - sitemap、meta 标签、语义化 URL
- **响应式设计** - 手机/平板/电脑自适应

## 📁 项目结构

```
gameguide-site/
├── _config.yml           # 主配置文件
├── _config.fluid.yml     # Fluid 主题配置
├── vercel.json           # Vercel 部署配置
├── source/
│   ├── _posts/           # 攻略文章（Markdown）
│   ├── about/            # 关于页面
│   ├── search/           # 搜索页面
│   ├── css/ad.css        # 广告位样式
│   └── js/ad.js          # 广告位脚本（待替换为实际广告代码）
├── .github/workflows/    # GitHub Actions 自动部署
└── scaffolds/            # 文章模板
```

## 📝 已有攻略文章

1. **黑神话悟空全Boss打法攻略** - 每个Boss弱点详解
2. **艾尔登法环DLC黄金树幽影全攻略** - 新区域探索指南
3. **塞尔达传说王国之泪全神庙攻略** - 152个神庙位置与解法
4. **博德之门3最佳职业搭配攻略** - 全12职业Build推荐

## 🚀 本地运行

```bash
# 进入项目目录
cd gameguide-site

# 安装依赖
npm install

# 本地预览
npx hexo server

# 生成静态文件
npx hexo generate
```

访问 http://localhost:4000 查看网站

## ✍️ 写新文章

```bash
# 创建新文章
npx hexo new "文章标题"

# 文章头部模板（Front Matter）：
---
title: 文章标题
date: 2026-05-14 12:00:00
categories:
  - 游戏分类（如 elden-ring）
tags:
  - 标签1
  - 标签2
description: 文章简介（SEO用）
keywords: 关键词1,关键词2
---
```

## 📂 分类 slug 映射

| 中文名 | slug（URL路径） |
|--------|----------------|
| 艾尔登法环 | elden-ring |
| 黑神话悟空 | black-myth-wukong |
| 塞尔达传说 | zelda |
| 博德之门3 | baldurs-gate-3 |
| 赛博朋克2077 | cyberpunk-2077 |
| 对马岛之魂 | ghost-of-tsushima |
| 荒野大镖客2 | red-dead-redemption-2 |
| 只狼 | sekiro |
| 星空 | starfield |
| 原神 | genshin-impact |

添加新游戏分类：编辑 `_config.yml` 中的 `category_map` 部分

## 🌐 部署到 Vercel（免费）

### 方法一：通过 Vercel CLI

```bash
# 安装 Vercel CLI
npm i -g vercel

# 登录
vercel login

# 部署
cd gameguide-site
npx hexo generate
vercel --prod
```

### 方法二：通过 GitHub + Vercel（推荐）

1. 将项目推送到 GitHub
2. 登录 vercel.com
3. 点击 "Import Project" → 选择 GitHub 仓库
4. Build Command: `npx hexo generate`
5. Output Directory: `public`
6. 点击 Deploy

部署成功后会得到一个 `xxx.vercel.app` 的免费域名。

### 绑定自定义域名（可选）

1. 在域名注册商购买域名（约 60 元/年）
2. 在 Vercel 项目设置中添加域名
3. 在域名注册商添加 CNAME 记录指向 `cname.vercel-dns.com`

## 💰 广告变现

### 百度联盟（推荐国内流量）

1. 注册：https://union.baidu.com
2. 创建广告位，获取代码
3. 将代码粘贴到 `source/js/ad.js` 中

### Google AdSense（推荐海外流量）

1. 注册：https://www.google.com/adsense
2. 创建广告单元
3. 将代码粘贴到 `source/js/ad.js` 中

广告位样式已预设在 `source/css/ad.css`，支持：
- 文章顶部横幅
- 文章底部横幅
- 侧边栏广告

## 📈 SEO 优化建议

1. **持续更新** - 每周至少 2-3 篇新攻略
2. **长尾关键词** - "黑神话悟空黑熊精怎么打" 比泛词更容易排名
3. **内链建设** - 文章之间互相链接
4. **图片优化** - 添加 alt 标签
5. **提交收录** - 
   - 百度站长：https://ziyuan.baidu.com
   - Google Search Console：https://search.google.com/search-console
6. **sitemap 已自动生成** - 部署后提交 `/sitemap.xml`

## 🔧 常用命令速查

| 操作 | 命令 |
|------|------|
| 新建文章 | `npx hexo new "标题"` |
| 本地预览 | `npx hexo server` |
| 生成静态 | `npx hexo generate` |
| 清理缓存 | `npx hexo clean` |
| 部署 | `vercel --prod` |
