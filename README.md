# OrangeTV 部署模板 (Fly.io)

这是一个使用 [Fly.io](https://fly.io) 部署 **OrangeTV** 应用的模板仓库，支持自动化 GitHub Actions 部署，并通过 **Secrets** 管理敏感信息，避免凭据泄露。

---

## ✨ 功能

- 使用 `ghcr.io/djteang/orangetv:latest` 官方镜像
- 自动化部署：支持 **GitHub Actions** 一键部署
- 免费额度内运行：`shared-cpu-1x` + `256MB RAM`
- 环境变量统一通过 **Secrets** 管理，安全可靠
- 支持 Redis Upstash 存储，无需磁盘挂载

---

## 🚀 部署流程

### 1. Fork 仓库
点击右上角 **Fork**，将本仓库复制到你自己的 GitHub 账户。

---

### 2. 创建 Fly.io 应用
在本地安装 [Fly CLI](https://fly.io/docs/hands-on/install-flyctl/)，并执行：


flyctl launch --name orangetv-app --no-deploy



---

### 3. 配置 GitHub Secrets

进入 GitHub → Settings → Secrets and variables → Actions，新增以下 secrets：
FLY_API_TOKEN	Fly.io API Token（用 flyctl auth token 获取）

### FLY令牌
```
FLY_API_TOKEN
```

### 站长账号
```
USERNAME
```

### 站长密码
```
PASSWORD
```

### 站点 url
```
SITE_BASE
```

### 站点名称	
```
NEXT_PUBLIC_SITE_NAME
```

### 站点公告
```
ANNOUNCEMENT
```

### 播放记录/收藏的存储方式
```
NEXT_PUBLIC_STORAGE_TYPE
```

### upstash redis 连接 url
```
UPSTASH_URL
```

### upstash redis 连接 token
```
UPSTASH_TOKEN
```

### 搜索接口可拉取的最大页数
```
NEXT_PUBLIC_SEARCH_MAX_PAGE
```

### 豆瓣数据源请求方式
```
NEXT_PUBLIC_DOUBAN_PROXY_TYPE
```

### 是否开启搜索接口流式输出
```
NEXT_PUBLIC_FLUID_SEARCH
```
```
