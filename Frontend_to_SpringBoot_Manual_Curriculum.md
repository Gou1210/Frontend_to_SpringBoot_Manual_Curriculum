# AI 时代前端转 Spring Boot 全栈开发手册：从 TypeScript 到 Java 的丝滑迁移

> **课程哲学**：在 AI 时代，学习 Spring Boot 不应沉溺于琐碎的 XML 配置或底层字节码，而应聚焦于“注解（Annotations）”与“分层架构（Layered Architecture）”。掌握了这两点，配合 AI 工具，前端开发者可以快速构建出高质量、工业级的 Java 后端服务。

---

## 课程核心目标
1. **降维打击**：利用 JS/TS 的深厚功底，快速理解 Java 核心概念。
2. **抓大放小**：放弃陈旧的 JavaEE 细枝末节，直击 Spring Boot 现代开发核心。
3. **AI 赋能**：学会如何利用 AI (Cursor/ChatGPT/Copilot) 编写、重构和测试 Java 代码。
4. **全栈视野**：建立从前端到后端的完整数据流认知。

---

## 目录大纲

### 第一章：AI 时代的 Java 开发新范式
*   **1.1 为什么是 Spring Boot？**
    *   企业级开发的“事实标准”。
    *   从 NestJS 视角看 Spring Boot：架构审美的惊人一致。
*   **1.2 AI 辅助开发的哲学**
    *   告别背诵 API：理解原理比记住语法更重要。
    *   AI 如何帮你搞定“模板代码”（Boilerplate）。
    *   如何给 AI 下达高质量的 Java 开发指令。

### 第二章：语言桥梁 —— 从 TypeScript 到 Java
*   **2.1 TS 高阶语法复习（Java 预备课）**
    *   **装饰器 (Decorators)**：Java 注解的前身，理解元数据编程。
    *   **泛型 (Generics)**：如何在 TS 和 Java 中编写可复用的类型。
    *   **接口与抽象类**：契约式编程的核心。
    *   **依赖注入 (DI)**：从 NestJS 的 `@Injectable()` 到 Spring 的 `@Service`。
*   **2.2 Java 语法精要（前端友好版）**
    *   **一切皆对象**：Java 的类结构。
    *   **Lombok：前端的“救星”**：通过注解消除 Getter/Setter，让 Java 代码像 TS 一样简洁。
    *   **访问修饰符**：`public`, `private`, `protected` 在大型项目中的意义。
    *   **集合框架**：JS Array/Map vs Java List/Set/Map。
    *   **函数式编程**：Java Stream API vs JS 数组方法 (`map`, `filter`, `reduce`)。
*   **2.3 工程解剖：Java 项目的“骨架”**
    *   **Maven/Gradle vs NPM**：理解依赖管理与构建生命周期。
    *   **标准目录结构**：为什么 Java 喜欢套这么多层文件夹 (`src/main/java/com/example...`)？
    *   **启动类与入口**：理解 `public static void main` 与 Spring Boot 的启动过程。

### 第三章：从“手动”到“自动” —— 核心心智模型切换
*   **3.1 什么是控制反转 (IoC)？**
    *   在 Express/Koa 中：你调用框架。
    *   在 Spring 中：框架调用你。
    *   为什么我们不再写 `new Service()`：理解“对象池”与“依赖注入 (DI)”。
*   **3.2 注解到底是什么？**
    *   **注解 = 贴在代码上的“便利贴”**：它本身不运行，是给 Spring 读的元数据。
    *   **反射 (Reflection) 浅析**：Spring 是如何像“侦探”一样扫描你的代码并执行逻辑的。
    *   **声明式编程**：从“如何做”到“想要什么”。
*   **3.3 配置管理：从 `.env` 到 `application.yml`**
    *   **YAML 层次感**：更直观的配置管理。
    *   **多环境切换 (Profiles)**：`dev`, `test`, `prod` 如何丝滑切换。
*   **3.4 “Bean” 到底是个啥？**
    *   Bean 就是被 Spring “托管”的对象，类似于 NestJS 的 `Provider`。
    *   理解单例 (Singleton) 与作用域：为什么大多数 Service 都是“一处定义，到处共用”。
*   **3.5 并发模型：多线程 vs 事件循环**
    *   **Java 的“分身术”**：理解 Thread-per-request 模型。
    *   **前端避坑指南**：为什么在 Java 中要小心使用全局变量。

### 第四章：Spring Boot 的灵魂 —— 核心注解 (Annotations)
*   **4.1 Web 层注解：构建 API 的“路由器”**
    *   `@RestController`: 声明一个 API 控制器。
    *   `@RequestMapping`, `@GetMapping`, `@PostMapping`: 定义路由映射。
    *   `@RequestBody`, `@RequestParam`, `@PathVariable`: 参数绑定艺术。
*   **4.2 逻辑层注解：依赖注入的“魔法棒”**
    *   `@Service` & `@Component`: 注册你的业务逻辑。
    *   `@Autowired`: 自动装配，消除手动实例化的痛苦。
    *   `@Value` & `@ConfigurationProperties`: 优雅地读取配置。
*   **4.3 数据层与配置注解**
    *   `@Configuration` & `@Bean`: 手动控制对象创建。
    *   `@Entity` & `@Table`: 让类与数据库表“对齐”。
    *   `@Transactional`: 一行代码搞定数据库事务（前端最向往的功能）。

### 第五章：架构脊梁 —— 标准四层架构
*   **5.1 为什么要分层？**
    *   解耦、可测试性与团队协作。
    *   前端视角的分层：Hook -> Service -> API。
*   **5.2 深入四层模型**
    *   **Controller (表现层)**：请求入口与参数校验。
    *   **Service (业务逻辑层)**：最核心的领域逻辑。
    *   **Mapper/Repository (持久层)**：与数据库的最后一步对话。
    *   **Entity/DTO/VO (模型层)**：数据的各种“变身”形态。
*   **5.3 连接点：一个请求的“一生”**
    *   **请求全链路分析**：从前端 Fetch 到后端 DB，再返回前端的完整路径。
    *   **利用 AI 快速生成 DTO 与 Entity 的转换逻辑**：MapStruct 还是 BeanUtils？AI 选哪个。

### 第六章：数据持久化 —— 让数据“落袋为安”
*   **6.1 数据库选型**：MySQL 依然是全栈开发者的首选。
*   **6.2 MyBatis-Plus：前端最爱的 Java ORM**
    *   为什么不推荐 JPA 而推荐 MyBatis-Plus？
    *   SQL 优先 vs 对象优先。
    *   利用 AI 编写复杂的 SQL 与 Wrapper 查询。
*   **6.3 Redis 缓存**：提升系统性能的“银弹”。

### 第七章：AI 驱动的实战工作流
*   **7.1 Prompt Engineering for Spring Boot**
    *   如何让 AI 生成 a 完美的 CRUD。
    *   如何让 AI 帮你重构臃肿的 Service。
*   **7.2 异常处理与日志**
    *   `@RestControllerAdvice`: 全局异常拦截（不再有 try-catch 噩梦）。
    *   SLF4J 日志：记录系统的点点滴滴。
*   **7.3 单元测试：AI 的强项**
    *   JUnit 5 & Mockito 基础。
    *   让 AI 帮你写出 80% 覆盖率的测试代码。

### 第八章：项目实战与部署
*   **8.1 从零搭建一个 RESTful API 服务**
    *   用户认证 (JWT) 与权限管理。
    *   图片上传与静态资源处理。
*   **8.2 前后端联调**
    *   跨域 (CORS) 处理。
    *   Swagger/OpenAPI 自动生成文档。
*   **8.3 部署与运维**
    *   Docker 容器化部署。
    *   CI/CD 基础概念。

---

## 附录：JS/TS vs Java 核心概念对照表
| 概念 | TypeScript (NestJS) | Java (Spring Boot) |
| :--- | :--- | :--- |
| 定义类/模块 | `@Module()`, `@Injectable()` | `@Component`, `@Service` |
| 定义控制器 | `@Controller()` | `@RestController` |
| 路由映射 | `@Get()`, `@Post()` | `@GetMapping`, `@PostMapping` |
| 属性注入 | `constructor(private srv: Srv)` | `@Autowired` 或 构造器注入 |
| 数据库映射 | TypeORM `@Entity()` | JPA `@Entity()` / MyBatis-Plus |
| 配置文件 | `.env`, `config.ts` | `application.yml` |
| 异常拦截 | `Exception Filter` | `@RestControllerAdvice` |
