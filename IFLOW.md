# ezBookkeeping 项目概览

## 项目简介

ezBookkeeping 是一个轻量级、自托管的个人财务管理应用，具有用户友好的界面和强大的记账功能。它易于部署，只需一个 Docker 命令即可启动。该项目专为资源效率和高可扩展性而设计，可以在低至树莓派的小型设备上平稳运行，也可以扩展到 NAS、微型服务器甚至大型集群环境。

## 技术栈

- **后端**: Go 语言 (Gin 框架)
- **前端**: Vue 3, TypeScript, Vuetify, Framework7
- **数据库**: 支持 SQLite, MySQL, PostgreSQL
- **构建工具**: Vite, NPM, Go Modules
- **容器化**: Docker

## 项目架构

ezBookkeeping 采用前后端分离架构。后端使用 Go 语言和 Gin 框架构建 RESTful API，前端使用 Vue 3 和 TypeScript 构建响应式用户界面。项目支持移动端和桌面端两种不同的 UI 体验。

## 构建与运行

### 依赖项

- **后端**: Go 1.25+, GCC
- **前端**: Node.js 24+, NPM
- **容器**: Docker (用于构建 Docker 镜像)

### 构建命令

项目提供了 `build.sh` 脚本来简化构建过程。

- **构建后端**: `./build.sh backend`
- **构建前端**: `./build.sh frontend`
- **构建发布包**: `./build.sh package`
- **构建 Docker 镜像**: `./build.sh docker`

### 运行应用

- **使用 Docker 运行**:
  ```bash
  docker run -p8080:8080 mayswind/ezbookkeeping
  ```
- **从二进制文件运行**:
  ```bash
  ./ezbookkeeping server run
  ```
- **从源码运行**:
  ```bash
  ./build.sh package -o ezbookkeeping.tar.gz
  # 解压并运行 ezbookkeeping 二进制文件
  ```

### 开发约定

- **代码风格**: 
  - 后端遵循 Go 语言标准风格，使用 `go vet` 进行检查。
  - 前端使用 ESLint 和 TypeScript 进行代码检查。
- **测试**:
  - 后端使用 Go 内置的 `testing` 包进行单元测试。
  - 前端使用 Jest 进行单元测试。
- **提交信息**: 遵循常规的 Git 提交信息格式。