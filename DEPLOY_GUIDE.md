# 🚀 CF Worker 部署指南 - 老王修复版

> 草！这个部署指南是老王专门为了修复那些SB错误写的，按步骤来就不会报错！

## 📋 部署前准备

### 1. Fork项目（已完成）
✅ 你已经fork了项目到 `qw31415/sublink-worker`

### 2. 创建KV命名空间

在部署前，你需要在CF Dashboard创建KV命名空间：

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 选择你的账号 → Workers & Pages → KV
3. 点击 "Create a namespace"
4. 命名空间名称建议：`sublink-kv`
5. 创建成功后，复制 **Namespace ID**（一串长字符串）

### 3. 修改配置文件

**重要！！！** 部署前必须修改 `wrangler.toml` 文件：

```toml
#:schema node_modules/wrangler/config-schema.json
name = "my-sublink-worker"  # 改成你想要的Worker名称
main = "src/index.js"
compatibility_date = "2024-07-24"
compatibility_flags = ["nodejs_compat"]

kv_namespaces = [
  { binding = "SUBLINK_KV", id = "YOUR_KV_NAMESPACE_ID" }  # 替换成你的KV ID
]
```

**必须替换的内容：**
- `name`: 改成你想要的Worker名称（建议包含你的用户名避免冲突）
- `YOUR_KV_NAMESPACE_ID`: 替换成第2步创建的KV命名空间ID

## 🔧 部署步骤

### 方法一：CF Pages部署（推荐）

1. 访问 [CF Workers & Pages](https://dash.cloudflare.com/?to=/:account/workers-and-pages/create)
2. 选择 "Create application" → "Pages" → "Connect to Git"
3. 选择你fork的 `qw31415/sublink-worker` 仓库
4. 部署设置：
   - **Framework preset**: None
   - **Build command**: `npm run deploy`
   - **Build output directory**: 保持空白
   - **Root directory**: 保持空白
5. 点击 "Save and Deploy"

### 方法二：本地wrangler部署

```bash
# 1. 克隆你的仓库
git clone https://github.com/qw31415/sublink-worker.git
cd sublink-worker

# 2. 安装依赖
npm install

# 3. 登录CF（如果没登录）
npx wrangler auth

# 4. 部署
npm run deploy
```

## ⚠️ 常见错误修复

### 错误1：Worker名称冲突
```
The name in your wrangler.toml file must match the name of your Worker
```
**解决**：修改`wrangler.toml`中的`name`字段为唯一名称

### 错误2：KV命名空间ID错误
```
Could not find KV namespace with id
```
**解决**：检查`wrangler.toml`中的KV ID是否正确

### 错误3：wrangler版本过旧
```
The version of Wrangler you are using is now out-of-date
```
**解决**：已修复，使用最新wrangler 4.30.0版本

## 🎯 部署后验证

部署成功后，访问你的Worker域名：
- `https://my-sublink-worker.你的CF用户名.workers.dev`

应该能看到Sublink Worker的Web界面。

## 📝 老王的碎碎念

这个项目本身挺牛逼的，就是CF部署时那些SB错误让人头疼。按照老王这个指南来，保证一次部署成功！要是还报错，那就是你没按步骤来，别怪老王没提醒你！

---
*修复by老王 - 一指禅敲代码的痞子流氓 2025-08-15*