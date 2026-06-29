# CF R2 云盘

基于 Cloudflare Workers + R2 + D1 的企业级文件存储系统，
支持通过 GitHub Actions 实现 Git Push 自动部署。

## 快速开始

### 1. 准备 Cloudflare 资源

```bash
# 创建 D1 数据库
npx wrangler d1 create r2-drive-db

# 创建 R2 存储桶
npx wrangler r2 bucket create my-r2-bucket

配置 GitHub Secrets
在仓库 Settings → Secrets → Actions 中添加：
Secret 名称	        说明
CF_API_TOKEN	Cloudflare API Token（需要 Worker+R2 权限）
CF_ACCOUNT_ID	Cloudflare 账号 ID
R2_BUCKET_NAME	R2 存储桶名称
ADMIN_TOKEN	    自定义访问密钥（登录密码）