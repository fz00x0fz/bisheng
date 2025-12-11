# Frontend 开发环境配置

本目录包含两个前端工程：
- **client** - 工作流编辑器 (端口 4001)
- **platform** - 管理平台 (端口 3001)

## 环境变量配置

开发人员可通过 `.env` 文件配置后端服务地址，无需修改 vite 配置文件。

### 配置步骤

1. 复制环境变量模板文件：
   ```bash
   cp .env.example .env
   ```

2. 编辑 `.env` 文件，配置你的后端服务地址：
   ```bash
   # 后端 API 服务地址
   VITE_PROXY_TARGET=http://127.0.0.1:7860

   # 文件服务地址 (可选，默认使用 VITE_PROXY_TARGET)
   VITE_FILE_SERVICE_TARGET=http://127.0.0.1:9101
   ```

### 环境变量说明

| 变量名 | 说明 | 默认值 |
|--------|------|--------|
| `VITE_PROXY_TARGET` | 后端 API 服务地址 | `http://127.0.0.1:7860` |
| `VITE_FILE_SERVICE_TARGET` | 文件服务地址 | 同 `VITE_PROXY_TARGET` |

## 启动开发服务

```bash
# 安装依赖 (首次)
npm install

# 启动 client 工程
cd client
npm start

# 启动 platform 工程
cd platform
npm start
```

## 注意事项

- `.env` 文件已加入 `.gitignore`，不会被提交到代码仓库
- 每位开发人员需根据自己的环境创建 `.env` 文件
- 修改 `.env` 后需重启开发服务器才能生效
