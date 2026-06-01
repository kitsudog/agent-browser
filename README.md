# agent-browser Docker Image

基于 Alpine Linux + Chromium + Node.js 的 Docker 镜像，用于运行 [agent-browser](https://github.com/ETOgaosion/agent-browser) CLI 工具。

## 镜像特点

- **轻量**：基于 Alpine Linux，镜像体积小巧
- **安全**：使用非 root 用户（`chrome`）运行
- **预装**：已内置 Chromium 浏览器，无需额外下载
- **平台**：支持 `linux/amd64`

## 使用方法

### 从 Docker Hub 拉取

```bash
docker pull <username>/agent-browser:latest
```

### 运行容器

```bash
docker run --rm <username>/agent-browser --help
```

### 本地构建

```bash
docker build -f .ci/Dockerfile -t agent-browser .
```

## 环境变量

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `AGENT_BROWSER_EXECUTABLE_PATH` | `/usr/bin/chromium-browser` | Chromium 浏览器可执行文件路径 |

## 项目结构

```
.
├── .ci/
│   └── Dockerfile          # Docker 镜像构建文件
└── .github/
    └── workflows/
        └── docker-build-push.yml  # GitHub Actions 自动构建推送
```

## 许可证

与上游 [agent-browser](https://github.com/ETOgaosion/agent-browser) 项目保持一致。
