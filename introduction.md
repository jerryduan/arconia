# Arconia Framework 项目介绍

## 项目概述

Arconia 是一个专为构建现代企业应用程序而设计的Java框架，基于Spring Boot构建，专注于提升开发者体验和云原生架构支持。该框架目前正在积极开发中，版本为 0.16.0-SNAPSHOT。







## 主要特性

### 🎯 核心目标
- **现代企业应用开发**: 为Java和Spring Boot应用提供企业级功能
- **云原生架构**: 原生支持云原生部署和架构模式
- **开发者体验**: 专注于提升开发效率和使用体验

### 🔧 技术要求
- Java 21+
- Spring Boot 3.5+








## 项目架构

### 核心模块 (arconia-core)
框架的基础核心模块，提供：
- **配置适配器**: PropertyAdapter类用于将外部配置源（如OpenTelemetry环境配置）转换为Arconia识别的属性
- **主机信息**: HostInfo类提供运行环境的主机信息
- **注解支持**: 提供Internal和Incubating注解用于API生命周期管理

### 开发服务 (arconia-dev)
为开发环境提供丰富的服务支持，基于Testcontainers实现：

#### 支持的数据库
- **MySQL**: arconia-dev-services-mysql
- **MariaDB**: arconia-dev-services-mariadb  
- **PostgreSQL**: arconia-dev-services-postgresql
- **Oracle**: arconia-dev-services-oracle (免费版)
- **Oracle XE**: arconia-dev-services-oracle-xe

#### 支持的中间件
- **Redis**: arconia-dev-services-redis
- **RabbitMQ**: arconia-dev-services-rabbitmq

#### 支持的AI/监控服务
- **Ollama**: arconia-dev-services-ollama (本地LLM服务)
- **LGTM**: arconia-dev-services-lgtm (日志、图形、跟踪和指标栈)
- **Docling**: arconia-dev-services-docling (文档处理服务)

### 集成模块 (arconia-integrations)

#### Docling集成 (arconia-docling)
提供与Docling文档处理服务的集成：
- **DoclingClient**: RESTful客户端接口，支持健康检查和文档转换
- **自动配置**: 自动配置Docling客户端连接
- **健康指标**: 集成Spring Boot Actuator健康检查
- **Testcontainers支持**: 开发和测试环境的容器化支持

### 可观测性 (arconia-observability)

#### OpenTelemetry集成
提供完整的可观测性解决方案：

**arconia-opentelemetry**:
- 完整的OpenTelemetry SDK集成
- 支持traces、metrics和logs的收集和导出
- OTLP导出器支持
- Micrometer桥接支持

**arconia-opentelemetry-logback-bridge**:
- Logback日志与OpenTelemetry的桥接

**arconia-opentelemetry-micrometer-metrics-bridge**:
- Micrometer指标与OpenTelemetry的桥接

### 多租户支持 (arconia-multitenancy)

#### 核心多租户功能 (arconia-multitenancy-core)
- **TenantContextHolder**: 线程安全的租户上下文管理
- **TenantDetails**: 租户信息抽象和实现
- **TenantDetailsService**: 租户数据访问层
- **PropertiesTenantDetailsService**: 基于配置文件的租户管理

#### Web多租户支持 (arconia-multitenancy-web)
- **TenantContextFilter**: Web请求的租户上下文过滤器
- **HeaderTenantResolver**: 基于HTTP头的租户解析
- **FixedTenantResolver**: 固定租户解析器

### Kubernetes支持 (arconia-kubernetes)

#### 服务绑定 (arconia-kubernetes-service-binding)
- 支持Kubernetes服务绑定规范
- 简化云原生环境中的服务发现和配置

### Spring Boot集成 (arconia-spring-boot)
提供与Spring Boot的深度集成：
- 自动配置支持
- 启动器模块
- Spring Boot特性增强

### Spring Boot启动器
提供便捷的依赖管理：

- **arconia-spring-boot-starter**: 基础启动器
- **arconia-docling-spring-boot-starter**: Docling集成启动器
- **arconia-multitenancy-web-spring-boot-starter**: Web多租户启动器
- **arconia-opentelemetry-spring-boot-starter**: OpenTelemetry可观测性启动器







## 构建和部署

### 构建工具
- **Gradle**: 使用Gradle作为构建工具
- **多模块项目**: 采用多模块Maven/Gradle项目结构
- **代码质量**: 集成代码质量检查和SBOM生成

### 发布信息
- **Group ID**: io.arconia
- **当前版本**: 0.16.0-SNAPSHOT
- **许可证**: Apache License 2.0






## 文档和资源

### 官方文档
- **在线文档**: https://arconia.io/docs/arconia/latest/index.html
- **示例项目**: https://github.com/arconia-io/arconia-examples

### 开发资源
- **Antora文档**: 使用Antora构建的模块化文档
- **API生命周期**: 提供Incubating和Internal注解标记API稳定性

### 社区和支持
- **GitHub**: arconia-io/arconia
- **Bluesky**: @arconia.io
- **安全报告**: 参见SECURITY.md






## 快速开始

1. **环境准备**: 确保Java 21+和Spring Boot 3.5+环境
2. **依赖添加**: 根据需要添加相应的starter依赖
3. **配置应用**: 配置所需的服务和功能
4. **运行应用**: 启动Spring Boot应用





## 注意事项

> **重要提示**: Arconia Framework目前正在积极开发中，我们正在努力改进它，感谢您在我们完善工具时的耐心。欢迎试用并分享您的反馈！

该框架特别适合：
- 需要多租户支持的企业应用
- 需要完整可观测性的云原生应用  
- 需要AI/LLM集成的现代应用
- 需要简化开发环境配置的团队

通过Arconia Framework，开发者可以快速构建具有企业级特性的现代Java应用程序，同时享受优秀的开发体验和云原生支持。
