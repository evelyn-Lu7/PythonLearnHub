# Python学习平台

一个功能完整的 Python 编程学习 Web 应用，提供在线学习、代码练习和在线判题功能。

## 快速开始

### 安装依赖

```bash
pip install -r requirements.txt
```

### 启动应用

```bash
python app.py
```

应用将在 `http://localhost:5000` 启动。

## 主要功能

- **学习模块** - 涵盖变量、字符串、列表、元组、流程控制、函数、异常、文件操作、正则表达式等
- **代码练习场** - 在线 Python 代码执行环境
- **在线判题系统** - 支持代码提交和自动判题
- **学习笔记** - 记录学习笔记，支持搜索
- **个人主页** - 学习统计、进度跟踪、活跃度图表

## 技术栈

- **后端**: Flask, SQLAlchemy
- **前端**: Bootstrap, JavaScript
- **数据库**: SQLite

## 项目结构

```
Project/
├── app.py                 # 主应用文件
├── models/                # 数据模型
│   ├── user.py           # 用户模型
│   ├── user_profile.py   # 用户配置模型
│   ├── progress.py       # 学习进度模型
│   ├── notes.py          # 笔记模型
│   ├── code_execution.py # 代码执行记录模型
│   └── problem.py        # 题目和提交模型
├── utils/                 # 工具模块
│   ├── safe_executor.py  # 安全代码执行器
│   ├── judge.py          # 判题引擎
│   └── module_content.py # 学习模块内容
├── templates/             # HTML 模板
├── static/                # 静态资源（CSS、JS、图片等）
├── Data/                  # 题目数据文件
├── deployment/            # 部署配置文件
│   ├── nginx_app.conf    # Nginx 配置
│   └── python-hub.service # systemd 服务配置
├── docker-compose.yml     # Docker Compose 配置
├── Dockerfile             # Docker 镜像配置
└── requirements.txt       # Python 依赖
```

## 部署方式

### Docker 部署

使用 Docker Compose 一键部署：

```bash
docker-compose up -d
```

应用将在 `http://localhost:5000` 启动。

### Nginx + Gunicorn 部署

使用 Nginx 作为反向代理，Gunicorn 作为 WSGI 服务器：

1. 配置 Nginx（参考 `deployment/nginx_app.conf`）
2. 配置 systemd 服务（参考 `deployment/python-hub.service`）
3. 启动服务：

```bash
sudo systemctl start python-hub
sudo systemctl enable python-hub
```

详细部署说明请参考 `docs/` 目录下的文档。
