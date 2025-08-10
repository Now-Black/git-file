# EasyPan 企业文件存储平台

## 🚀 项目简介

EasyPan 是一个基于 Spring Boot 的企业级文件存储平台，提供安全、高效的文件管理解决方案。系统支持文件上传、下载、预览、分享等核心功能，适用于企业内部文件管理和协作。

## ✨ 核心功能

- **文件管理**：支持文件/文件夹的增删改查、重命名、移动等操作
- **文件上传**：支持分片上传、断点续传，最大支持 15MB 单文件
- **文件预览**：支持图片、文档等多种格式的在线预览
- **文件分享**：灵活的文件分享机制，支持分享链接和权限控制
- **回收站**：删除文件的回收和恢复功能
- **用户管理**：完整的用户注册、登录、权限管理体系
- **邮件服务**：邮箱验证码发送，找回密码等功能
- **QQ 登录**：支持第三方 QQ 快速登录
- **系统监控**：文件清理任务、系统日志管理

## 🛠️ 技术栈

### 后端技术
- **Java 8** - 核心开发语言
- **Spring Boot 2.6.1** - 主框架
- **MyBatis** - 数据持久层
- **MySQL 8.0** - 数据库
- **Redis** - 缓存和消息队列
- **RabbitMQ** - 消息队列（可选）
- **AspectJ** - AOP 切面编程
- **Logback** - 日志管理

### 工具库
- **FastJSON** - JSON 处理
- **Apache Commons** - 工具类库
- **OkHttp** - HTTP 客户端
- **HikariCP** - 数据库连接池
- **Spring Mail** - 邮件发送

## 📁 项目结构

```
src/main/java/com/easypan/
├── annotation/          # 自定义注解
├── aspect/             # AOP 切面
├── component/          # 组件
├── controller/         # 控制器层
├── entity/             # 实体类
│   ├── config/         # 配置类
│   ├── constants/      # 常量定义
│   ├── dto/           # 数据传输对象
│   ├── enums/         # 枚举类
│   ├── po/            # 持久化对象
│   ├── query/         # 查询对象
│   └── vo/            # 视图对象
├── exception/          # 异常处理
├── mappers/           # MyBatis 映射器
├── service/           # 业务逻辑层
├── task/              # 定时任务
└── utils/             # 工具类
```

## 🚀 快速开始

### 环境要求
- JDK 8+
- MySQL 8.0+
- Redis 6.0+
- Maven 3.6+

### 安装步骤

1. **克隆项目**
```bash
git clone [your-repository-url]
cd Ele-java
```

2. **数据库配置**
- 创建数据库 `easypan`
- 修改 `application.properties` 中的数据库配置

3. **Redis 配置**
- 启动 Redis 服务
- 修改 `application.properties` 中的 Redis 配置

4. **构建运行**

```bash
mvn clean package
java -jar target/easypan-1.0.jar
```

### 配置说明

主要配置文件 `application.properties`：
- **服务端口**：8080
- **数据库连接**：MySQL 配置
- **Redis 连接**：缓存配置
- **邮件服务**：SMTP 配置
- **文件路径**：文件存储目录配置
- **QQ 登录**：第三方登录配置

## 🔧 核心配置

```properties
# 服务配置
server.port=8080
server.servlet.context-path=/api

# 文件上传配置
spring.servlet.multipart.max-file-size=15MB
spring.servlet.multipart.max-request-size=15MB

# 数据库配置
spring.datasource.url=jdbc:mysql://localhost:3306/easypan
spring.datasource.username=root
spring.datasource.password=root

# Redis 配置
spring.redis.host=127.0.0.1
spring.redis.port=6379

# 项目文件存储路径
project.folder=/usr/server/easypan
```

## 📚 API 文档

### 主要接口模块
- **文件管理**：`/api/file/*` - 文件的增删改查操作
- **用户管理**：`/api/account/*` - 用户注册登录相关
- **分享功能**：`/api/share/*` - 文件分享管理
- **回收站**：`/api/recycle/*` - 删除文件管理
- **管理后台**：`/api/admin/*` - 系统管理功能

## 🛡️ 安全特性

- **参数验证**：全局参数校验和拦截
- **异常处理**：统一异常处理机制
- **文件安全**：文件类型校验和大小限制
- **用户认证**：Session 管理和权限控制
- **数据加密**：敏感数据加密存储

## 📝 开发说明

### 开发环境
```properties
# 开发环境标识
dev=true
# 项目本地路径
project.folder=e:/JavaProject/Ele-java-project/webapp/
```

### 日志配置
- 使用 Logback 进行日志管理
- 支持不同级别的日志输出
- 日志文件按日期分割存储

---

⭐ 如果这个项目对你有帮助，请给个 Star 支持一下！