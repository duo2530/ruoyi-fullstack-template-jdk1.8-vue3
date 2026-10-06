# RuoYi 全栈模板（JDK 8 + Vue 3）

若依前后端分离项目模板，包含 Java 管理后台、Vue 3 Web 管理端和 uni-app 移动端。仓库已配置为 GitHub 模板项目，可通过 GitHub 的 **Use this template** 创建自己的项目。

## 项目结构

```text
backend/          Spring Boot 后端（JDK 8）
frontend/pc-web/  Vue 3 + Vite 管理端
frontend/uni-app/ Vue 3 + uni-app 移动端（小程序、H5、App）
```

## 技术栈

- 后端：Java 8、Spring Boot 2.5、Spring Security、MyBatis、JWT、Redis、Maven
- Web 管理端：Vue 3、Vite、Element Plus、Pinia
- 移动端：Vue 3、uni-app、uni-ui
- 数据库：MySQL

## 环境要求

- JDK 8 和 Maven
- MySQL，以及 Redis
- Node.js 和 npm（Web 管理端）
- HBuilderX（uni-app 开发、运行和发行）

## 快速开始

### 1. 初始化数据库

创建 MySQL 数据库 `ry-vue`，导入 `backend/sql/ry_20260417.sql` 和 `backend/sql/quartz.sql`。按本地环境修改 `backend/ruoyi-admin/src/main/resources/application-druid.yml` 中的数据库地址、用户名和密码，并在 `backend/ruoyi-admin/src/main/resources/application.yml` 中配置 Redis。

### 2. 启动后端

在 IDE 中打开 `backend` Maven 项目，运行 `com.ruoyi.RuoYiApplication`；或在仓库根目录执行：

```bash
cd backend
mvn -pl ruoyi-admin -am spring-boot:run
```

后端默认监听 `http://localhost:8080`。

### 3. 启动 Web 管理端

```bash
cd frontend/pc-web
npm install
npm run dev
```

如需联调本地后端，确认 Vite 代理配置指向 `http://localhost:8080`。生产构建使用 `npm run build:prod`。

### 4. 运行移动端

使用 HBuilderX 打开 `frontend/uni-app`，选择目标平台运行或发行。小程序 appid 位于 `manifest.json` 的 `mp-weixin.appid` 字段；发布前请替换为自己的微信小程序 appid，并按目标平台配置应用标识和接口地址。接口配置位于 `frontend/uni-app/config.js`。

## 许可证

本项目采用 [MIT License](LICENSE)。后端及前端目录中的组件和依赖可能包含其各自的许可证，请在分发前一并核对。
