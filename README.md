# CICD GitLab CI 服务模板

这是一个用于GitLab CI/CD流水线的模板集合，提供了多种语言和技术栈的CI/CD配置模板。

## 目录结构

```
cidevops-gitlabci-service/
├── jobs/                 # CI作业模板
│   ├── artifactory.yml   # 制品库相关作业
│   ├── build.yml         # 构建作业模板
│   ├── codeanalysis.yml  # 代码分析作业
│   ├── deploy.yml        # 部署作业模板
│   └── test.yml          # 测试作业模板
└── templates/            # 流水线模板
    ├── android-pipeline.yml  # Android项目流水线
    ├── default-pipeline.yml  # 默认通用流水线
    ├── go-pipeline.yml       # Go语言项目流水线
    ├── java-pipeline.yml     # Java项目流水线
    └── web-pipeline.yml      # Web前端项目流水线
```

## 使用方法

### 1. 选择合适的流水线模板

根据不同项目类型选择对应的流水线模板：

- **Android项目**: 使用 `templates/android-pipeline.yml`
- **Go项目**: 使用 `templates/go-pipeline.yml`
- **Java项目**: 使用 `templates/java-pipeline.yml`
- **Web前端项目**: 使用 `templates/web-pipeline.yml`
- **通用项目**: 使用 `templates/default-pipeline.yml`

### 2. 在项目中引用

在你的项目根目录创建 `.gitlab-ci.yml` 文件，并引用相应的模板：

```yaml
include:
  - project: 'your-group/cidevops-gitlabci-service'
    ref: 'main'
    file: '/templates/go-pipeline.yml'
```

### 3. 自定义配置

根据需要修改模板中的变量和配置参数。

## 作业说明

### jobs/artifactory.yml
处理制品仓库相关的操作，包括：
- 制品上传
- 制品下载
- 版本管理

### jobs/build.yml
构建作业模板，支持：
- 多种编程语言构建
- 缓存管理
- 构建产物处理

### jobs/codeanalysis.yml
代码质量分析作业：
- 代码静态检查
- 安全扫描
- 代码覆盖率分析

### jobs/deploy.yml
部署作业模板：
- Kubernetes部署
- 蓝绿部署
- 滚动更新

### jobs/test.yml
测试作业模板：
- 单元测试
- 集成测试
- 端到端测试

## 贡献指南

欢迎提交Issue和Pull Request来改进这些模板。

## 许可证

MIT License