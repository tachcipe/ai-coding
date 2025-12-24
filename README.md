# AI Coding

基于 Issue 自动触发的 AI 编程助手，实现从需求到部署的全自动化流程。

## 🎯 项目愿景

打造一个智能化的开发工作流，让 AI 成为团队的编程助手，自动处理从需求分析到代码部署的完整流程。

## ✨ 核心功能

### 1. 🚀 基于 Issue 云端自动触发 AI Coding

- **Issue 监听**: 监控 GitHub/GitLab Issue 的创建和更新
- **智能解析**: AI 自动分析 Issue 内容，理解需求
- **代码生成**: 基于需求自动生成高质量代码
- **云端执行**: 在云端环境中安全执行 AI 编程任务

### 2. 🧪 自动测试

- **单元测试生成**: AI 自动为生成的代码编写单元测试
- **测试执行**: 自动运行测试套件
- **覆盖率检查**: 确保代码测试覆盖率达标
- **测试报告**: 生成详细的测试报告

### 3. 📝 自动提交 PR

- **分支管理**: 自动创建功能分支
- **代码提交**: 规范化的 commit message
- **PR 创建**: 自动创建 Pull Request
- **PR 描述**: AI 生成详细的 PR 描述，包含变更说明

### 4. 📧 邮件通知

- **状态通知**: 任务开始、进行中、完成状态通知
- **结果报告**: 测试结果、PR 链接等关键信息
- **异常告警**: 任务失败时及时通知相关人员
- **自定义配置**: 支持配置通知接收人和通知规则

### 5. 🔄 PR 合并后自动触发 CI/CD 部署

- **合并检测**: 监听 PR 合并事件
- **CI 流水线**: 自动触发构建和测试流水线
- **CD 部署**: 自动部署到指定环境
- **部署验证**: 部署后自动进行健康检查

## 🏗️ 系统架构

```
┌─────────────────────────────────────────────────────────────────┐
│                        GitHub/GitLab                            │
│  ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐      │
│  │  Issue  │───▶│ Webhook │───▶│   PR    │───▶│  Merge  │      │
│  └─────────┘    └─────────┘    └─────────┘    └─────────┘      │
└───────┬─────────────┬─────────────┬─────────────┬──────────────┘
        │             │             │             │
        ▼             ▼             ▼             ▼
┌─────────────────────────────────────────────────────────────────┐
│                      AI Coding Platform                         │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │   Issue     │  │    Code     │  │    Test     │             │
│  │  Analyzer   │  │  Generator  │  │   Runner    │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │     PR      │  │   Email     │  │   CI/CD     │             │
│  │   Creator   │  │  Notifier   │  │  Trigger    │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    Deployment Targets                           │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │    Dev      │  │   Staging   │  │ Production  │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
└─────────────────────────────────────────────────────────────────┘
```

## 📋 项目规划

### Phase 1: 基础架构搭建 (MVP)

- [ ] 项目初始化和基础框架搭建
- [ ] GitHub Webhook 接收和处理
- [ ] Issue 内容解析模块
- [ ] 基础 AI 代码生成集成

### Phase 2: 自动化测试

- [ ] 测试框架集成
- [ ] AI 自动生成测试用例
- [ ] 测试执行和结果收集
- [ ] 测试覆盖率报告

### Phase 3: PR 自动化

- [ ] Git 操作封装
- [ ] 自动创建分支和提交
- [ ] PR 创建和描述生成
- [ ] PR 状态追踪

### Phase 4: 通知系统

- [ ] 邮件服务集成
- [ ] 通知模板设计
- [ ] 通知规则配置
- [ ] 多渠道通知支持 (Slack/钉钉/企业微信)

### Phase 5: CI/CD 集成

- [ ] CI/CD 平台对接 (GitHub Actions/GitLab CI)
- [ ] 部署流水线配置
- [ ] 自动部署触发
- [ ] 部署状态监控和回滚

### Phase 6: 优化和扩展

- [ ] 性能优化
- [ ] 多仓库支持
- [ ] 权限和安全增强
- [ ] 监控和日志完善

## 🛠️ 技术栈

| 组件 | 技术选型 |
|------|----------|
| 后端服务 | Python / Node.js |
| AI 引擎 | OpenAI API / Claude API |
| 消息队列 | Redis / RabbitMQ |
| 数据存储 | PostgreSQL / MongoDB |
| CI/CD | GitHub Actions / GitLab CI |
| 容器化 | Docker / Kubernetes |
| 邮件服务 | SendGrid / AWS SES |

## 🚀 快速开始

```bash
# 克隆项目
git clone https://github.com/tachcipe/ai-coding.git
cd ai-coding

# 安装依赖
pip install -r requirements.txt

# 配置环境变量
cp .env.example .env
# 编辑 .env 文件，填入必要的配置

# 启动服务
python main.py
```

## ⚙️ 配置说明

```yaml
# config.yaml 示例
github:
  token: ${GITHUB_TOKEN}
  webhook_secret: ${WEBHOOK_SECRET}

ai:
  provider: openai  # openai / claude
  api_key: ${AI_API_KEY}
  model: gpt-4

notification:
  email:
    smtp_host: smtp.example.com
    smtp_port: 587
    sender: noreply@example.com
  recipients:
    - dev@example.com

deployment:
  environments:
    - name: staging
      auto_deploy: true
    - name: production
      auto_deploy: false
      require_approval: true
```

## 📖 工作流程

1. **Issue 创建** → 开发者在 GitHub 创建 Issue，描述需求
2. **AI 分析** → 系统自动解析 Issue，理解需求
3. **代码生成** → AI 生成符合需求的代码
4. **自动测试** → 运行测试确保代码质量
5. **创建 PR** → 自动创建 Pull Request
6. **通知** → 发送邮件通知相关人员
7. **代码审查** → 人工审查 PR
8. **合并部署** → PR 合并后自动触发部署

## 🤝 贡献指南

欢迎贡献代码！请查看 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详情。

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件