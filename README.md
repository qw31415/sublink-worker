<div align="center">
  <h1><b>Sublink Worker - 老王修复版</b></h1>
  <h5><i>Best Practice for Serverless Self-Deployed Subscription Conversion Tool</i></h5>
  
  <a href="https://trendshift.io/repositories/12291" target="_blank">
    <img src="https://trendshift.io/api/badge/repositories/12291" alt="7Sageer%2Fsublink-worker | Trendshift" width="250" height="55"/>
  </a>
  
  <br>

  <p>
    <a href="https://dash.cloudflare.com/?to=/:account/workers-and-pages/create">
      <img src="https://deploy.workers.cloudflare.com/button" alt="Deploy to Cloudflare Workers"/>
    </a>
  </p>
  
  <p><a href="/docs/README_CN.md">中文文档</a> | <a href="/DEPLOY_GUIDE.md">🔥 老王部署指南</a></p>
</div>

## 🚀 快速开始

### ⚠️ 重要提醒 - 老王修复版说明

**草！原版部署经常报错，老王已经修复了以下SB问题：**
- ✅ 修复CF Worker名称冲突错误
- ✅ 升级wrangler到最新版本避免警告
- ✅ 提供详细的KV配置说明
- ✅ 新增完整的错误修复指南

**👉 [点击查看详细部署指南](DEPLOY_GUIDE.md) - 按步骤来保证部署成功！**

### 快速部署
1. **必须先看** [部署指南](DEPLOY_GUIDE.md) 配置KV命名空间
2. 修改 `wrangler.toml` 中的Worker名称和KV ID
3. Fork本项目，点击上面的 `Deploy to Cloudflare` 按钮
4. 在 `Import Repository` 部分选择你的仓库（需要关联GitHub账号）
5. 修改 `Deploy Command` 如下，然后选择 `Save and Deploy`
``` bash
npm run deploy
```

## ✨ 功能特色

### 支持的协议
- ShadowSocks
- VMess
- VLESS
- Hysteria2
- Trojan
- TUIC

### 核心功能
- 支持导入Base64 http/https订阅链接和各种协议分享URL
- 纯JavaScript + Cloudflare Worker实现，一键部署，开箱即用
- 支持固定/随机短链接生成（基于KV）
- 明/暗主题切换
- 灵活的API，支持脚本操作
- 支持中文、英文、波斯语

### 客户端支持
- Sing-Box
- Clash
- Xray/V2Ray

### Web界面功能
- 用户友好的操作界面
- 多种预定义规则集
- 可自定义geo-site、geo-ip、ip-cidr、domain-suffix策略组

## 📖 API文档

详细API文档请参考 [APIDoc.md](/docs/APIDoc.md)

### 主要端点
- `/singbox` - 生成Sing-Box配置
- `/clash` - 生成Clash配置
- `/xray` - 生成Xray配置
- `/shorten` - 生成短链接

## 📝 最近更新

### 2025-08-15 - 老王修复版

- 🔥 修复CF Worker部署时名称冲突错误
- 🔥 升级wrangler到4.30.0版本避免过期警告
- 🔥 新增详细的部署指南和错误修复方案
- 🔥 优化KV命名空间配置说明

### 2025-05-02

- 当存在同名代理时现在会应用自动重命名 ([#175](https://github.com/7Sageer/sublink-worker/pull/175))
- 修复了Singbox的DNS配置 ([#174](https://github.com/7Sageer/sublink-worker/pull/174))

## 🔧 项目结构

```
.
├── index.js                 # 主服务器逻辑，处理请求路由
├── BaseConfigBuilder.js     # 构建基础配置
├── SingboxConfigBuilder.js  # 构建Sing-Box配置
├── ClashConfigBuilder.js    # 构建Clash配置
├── ProxyParsers.js          # 解析各种代理协议URL
├── utils.js                 # 提供各种实用函数
├── htmlBuilder.js           # 生成Web界面
├── style.js                 # 生成Web界面CSS
├── config.js                # 存储配置信息
├── DEPLOY_GUIDE.md          # 老王部署指南（新增）
└── docs/
    ├── APIDoc.md            # API文档
    ├── UpdateLogs.md        # 更新日志
    ├── FAQ.md               # 常见问题
    └── BaseConfig.md        # 基础配置功能介绍
```

## 🤝 贡献

欢迎提交Issues和Pull Requests来改进这个项目。

## 📄 许可证

本项目基于MIT许可证 - 详见 [LICENSE](LICENSE) 文件。

## ⚠️ 免责声明

本项目仅供学习交流使用，请勿用于非法用途。使用本项目产生的一切后果均由使用者本人承担，与开发者无关。

## 💰 赞助

<div align="center">
  <h3>感谢以下赞助商对本项目的支持</h3>
<table border="0">
  <tr>
    <td>
      <a href="https://yxvm.com/" target="_blank" title="YXVM">
        <img src="https://image.779477.xyz/yxvm.png" alt="YXVM" height="60" hspace="20"/>
      </a>
    </td>
    <td>
      <a href="https://github.com/NodeSeekDev/NodeSupport" target="_blank" title="NodeSupport">
        <img src="https://image.779477.xyz/ns.png" alt="NodeSupport" height="60" hspace="20"/>
      </a>
    </td>
  </tr>
</table>
  <p><b>NodeSupport has sponsored this project, thank you for your support!</b></p>
  <p>如果你想赞助这个项目，请联系开发者 <a href="https://github.com/7Sageer" style="text-decoration: none;">@7Sageer</a></p>
</div>

---

## 🔥 老王修复版特别说明

本版本由老王修复，专门解决CF Worker部署时的各种SB错误。老王一指禅敲代码，虽然嘴上骂骂咧咧，但代码质量杠杠的！

**遇到问题？** 先看 [部署指南](DEPLOY_GUIDE.md)，按步骤来就不会出错。要是还有问题，那就是你没好好看文档！

## ⭐ Star History

感谢每一个给这个项目点星的人！🌟

<a href="https://star-history.com/#7Sageer/sublink-worker&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=7Sageer/sublink-worker&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=7Sageer/sublink-worker&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=7Sageer/sublink-worker&type=Date" />
 </picture>
</a>