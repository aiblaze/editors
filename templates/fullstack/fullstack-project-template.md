# 全栈项目模板

## 项目初始化

### 必需工具
- Git
- Node.js (v22+)
- pnpm (v10+)
- Docker
- Cursor
- 数据库客户端 (如 DBeaver, pgAdmin)

### 开发工具配置

#### Cursor 推荐插件
- ESLint
- GitLens
- Docker
- REST Client
- Database Tools

#### ESLint 配置
```js
// eslint.config.js
import antfu from '@antfu/eslint-config'

export default antfu({
  // 启用 TypeScript 支持
  typescript: {
    tsconfigPath: 'tsconfig.json',
  },
  // 启用 Vue 支持（如果需要）
  vue: true,
  // 启用 React 支持（如果需要）
  react: true,
  // 启用 JSON 支持
  jsonc: true,
  // 启用 Markdown 支持
  markdown: true,
  // 启用 YAML 支持
  yaml: true,
  // 启用 Git 忽略文件支持
  gitignore: true,
  // 启用格式化器
  formatters: {
    // 格式化 CSS 文件
    css: true,
    // 格式化 HTML 文件
    html: true,
    // 格式化 Markdown 文件
    markdown: 'prettier'
  }
})
```

### 环境变量管理
```env
# .env.example
# 应用配置
APP_NAME=My Fullstack App
APP_ENV=development
APP_DEBUG=true

# 数据库配置
DB_HOST=localhost
DB_PORT=5432
DB_NAME=myapp
DB_USER=postgres
DB_PASSWORD=password

# API配置
API_BASE_URL=http://localhost:3000
API_VERSION=v1

# JWT配置
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=7d
```

## 项目结构

### 前端项目结构
```
frontend/
├── src/
│   ├── assets/          # 静态资源
│   ├── components/      # 可复用组件
│   │   ├── common/     # 通用组件
│   │   └── business/   # 业务组件
│   ├── composables/     # 组合式函数
│   ├── layouts/        # 布局组件
│   ├── pages/          # 页面组件
│   ├── router/         # 路由配置
│   ├── stores/         # 状态管理
│   ├── styles/         # 样式文件
│   ├── types/          # TypeScript 类型
│   └── utils/          # 工具函数
├── public/             # 公共资源
├── tests/              # 测试文件
├── .env.example        # 环境变量示例
├── package.json        # 项目配置
├── tsconfig.json       # TypeScript 配置
└── vite.config.ts      # Vite 配置
```

### 后端项目结构
```
backend/
├── src/
│   ├── config/         # 配置文件
│   ├── controllers/    # 控制器
│   ├── middleware/     # 中间件
│   ├── models/         # 数据模型
│   ├── routes/         # 路由
│   ├── services/       # 业务逻辑
│   ├── types/          # 类型定义
│   └── utils/          # 工具函数
├── tests/              # 测试文件
├── .env.example        # 环境变量示例
├── package.json        # 项目配置
├── tsconfig.json       # TypeScript 配置
└── docker-compose.yml  # Docker 配置
```

## 开发规范

### 代码规范
- 遵循 DRY (Don't Repeat Yourself) 原则
- 遵循 SOLID 原则
- 保持代码简洁清晰
- 编写自解释的代码
- 适当添加注释

### 命名规范
- 变量/函数：camelCase
- 类：PascalCase
- 常量：UPPER_SNAKE_CASE
- 文件名：kebab-case
- 组件名：PascalCase

### Git 工作流
```bash
# 主分支
main        # 生产环境分支
develop     # 开发环境分支

# 功能分支
feature/*   # 新功能分支
hotfix/*    # 紧急修复分支
release/*   # 发布分支
```

### 提交规范
```bash
# 提交格式
<type>(<scope>): <subject>

# 类型
feat:     新功能
fix:      修复bug
docs:     文档更新
style:    代码格式
refactor: 重构
test:     测试
chore:    构建过程或辅助工具的变动
```

## API 设计规范

### RESTful API 设计
```typescript
// 基础响应格式
interface ApiResponse<T> {
  code: number
  message: string
  data: T
  timestamp: string
}

// 错误响应格式
interface ApiError {
  code: number
  message: string
  errors?: Record<string, string[]>
  timestamp: string
}

// 分页响应格式
interface PaginatedResponse<T> extends ApiResponse<T> {
  data: {
    items: T[]
    total: number
    page: number
    pageSize: number
  }
}
```

### 路由规范
```typescript
// 路由版本控制
/api/v1/users
/api/v1/products
/api/v1/orders

// 资源关系
/api/v1/users/:userId/orders
/api/v1/products/:productId/reviews
```

## 数据库规范

### 命名规范
```sql
-- 表名
users
products
orders
order_items

-- 字段名
id
created_at
updated_at
deleted_at
user_id
product_id
```

### 索引规范
```sql
-- 主键索引
CREATE INDEX idx_users_id ON users(id);

-- 外键索引
CREATE INDEX idx_orders_user_id ON orders(user_id);

-- 复合索引
CREATE INDEX idx_orders_user_status ON orders(user_id, status);
```

## 安全规范

### 认证与授权
```typescript
// JWT 配置
interface JwtConfig {
  secret: string
  expiresIn: string
  refreshToken: {
    secret: string
    expiresIn: string
  }
}

// RBAC 权限控制
interface Permission {
  resource: string
  action: string
  conditions?: Record<string, any>
}
```

### API 安全
```typescript
// 请求限流配置
interface RateLimitConfig {
  windowMs: number
  max: number
  message: string
}

// CORS 配置
interface CorsConfig {
  origin: string | string[]
  methods: string[]
  allowedHeaders: string[]
  credentials: boolean
}
```

## 测试规范

### 测试配置
```typescript
// Vitest 配置
export default defineConfig({
  test: {
    globals: true,
    environment: 'node',
    coverage: {
      provider: 'v8',
      reporter: ['text', 'json', 'html'],
    },
  },
})
```

### 测试覆盖率要求
```json
{
  "statements": 80,
  "branches": 80,
  "functions": 80,
  "lines": 80
}
```

## 部署配置

### Docker 配置
```yaml
# docker-compose.yml
version: '3.8'
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production

  backend:
    build: ./backend
    ports:
      - "4000:4000"
    environment:
      - NODE_ENV=production
    depends_on:
      - db

  db:
    image: postgres:15
    ports:
      - "5432:5432"
    environment:
      - POSTGRES_DB=myapp
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=password
```

### CI/CD 配置
```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: pnpm/action-setup@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '22'
      - run: pnpm install
      - run: pnpm test
      - run: pnpm lint
```

## 监控配置

### 应用监控
```typescript
// 性能监控配置
interface MonitoringConfig {
  enabled: boolean
  sampleRate: number
  endpoints: {
    metrics: string
    traces: string
    logs: string
  }
}
```

### 日志配置
```typescript
// 日志配置
interface LogConfig {
  level: 'debug' | 'info' | 'warn' | 'error'
  format: 'json' | 'text'
  transports: {
    type: 'console' | 'file' | 'http'
    options: Record<string, any>
  }[]
}
```

## 参考资源
- [antfu/eslint-config](https://github.com/antfu/eslint-config)
- [Vue 3 文档](https://vuejs.org/)
- [React 文档](https://react.dev/)
- [Node.js 文档](https://nodejs.org/)
- [TypeScript 文档](https://www.typescriptlang.org/)
- [Docker 文档](https://docs.docker.com/) 