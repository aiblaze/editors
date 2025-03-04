# React 项目模板

## 项目初始化

### 使用 Vite 创建项目
```bash
pnpm create vite my-react-app --template react-ts
```

### 推荐的项目配置
- TypeScript: Yes
- ESLint: Yes
- Prettier: Yes
- Husky: Yes
- Commitlint: Yes
- Vitest: Yes
- Testing Library: Yes

## 项目结构
```
src/
├── assets/          # 静态资源
├── components/      # 可复用组件
│   ├── common/     # 通用组件
│   └── business/   # 业务组件
├── hooks/          # 自定义 hooks
├── layouts/        # 布局组件
├── pages/          # 页面组件
├── routes/         # 路由配置
├── stores/         # 状态管理
├── styles/         # 样式文件
├── types/          # TypeScript 类型
└── utils/          # 工具函数
```

## 开发规范

### 组件命名
- 文件名：PascalCase（如 `UserProfile.tsx`）
- 组件名：PascalCase（如 `UserProfile`）
- 基础组件：以 Base 开头（如 `BaseButton.tsx`）
- 页面组件：以 Page 结尾（如 `HomePage.tsx`）

### 组件结构
```tsx
import { FC, useState, useEffect } from 'react'
import type { Props } from './types'

export const ComponentName: FC<Props> = ({ title, items }) => {
  // 1. Hooks
  const [count, setCount] = useState(0)
  
  // 2. 副作用
  useEffect(() => {
    // 副作用逻辑
  }, [])
  
  // 3. 事件处理
  const handleClick = () => {
    setCount(prev => prev + 1)
  }
  
  // 4. 渲染
  return (
    <div className="component-name">
      {/* JSX 内容 */}
    </div>
  )
}
```

### 状态管理
- 使用 Zustand 或 Redux Toolkit
- 按功能模块拆分 store
- 使用 hooks 风格
- 保持 store 的单一职责

### 路由配置
- 使用 React Router
- 实现路由守卫
- 路由懒加载
- 路由权限控制

### 样式规范
- 使用 Tailwind CSS 或 styled-components
- 采用 CSS Modules 或 CSS-in-JS
- 使用 CSS 变量管理主题
- 响应式设计

### API 调用
- 使用 TanStack Query (React Query)
- 统一的请求拦截器
- 统一的错误处理
- 请求取消处理

### 性能优化
- 组件懒加载
- 图片懒加载
- 虚拟列表
- 合理的缓存策略

### 测试规范
- 单元测试：Vitest
- 组件测试：React Testing Library
- E2E 测试：Cypress
- 测试覆盖率要求

## 开发工具

### 推荐 VSCode 插件
- ESLint
- Prettier
- GitLens
- Error Lens
- Tailwind CSS IntelliSense

### 推荐浏览器插件
- React Developer Tools
- Redux DevTools

## 部署配置

### 构建优化
- 代码分割
- Tree Shaking
- 压缩优化
- CDN 配置

### 环境变量
```env
VITE_API_BASE_URL=http://api.example.com
VITE_APP_TITLE=My React App
```

## 常见问题解决

### 1. 组件通信
- Props 传递数据
- Context 跨层级通信
- 状态管理工具
- 自定义事件

### 2. 性能优化
- 使用 `useMemo` 和 `useCallback`
- 避免不必要的重渲染
- 使用 `React.memo`
- 合理使用 `useEffect` 依赖

### 3. 类型安全
- 使用 TypeScript 类型注解
- 定义接口和类型
- 使用类型断言
- 启用严格模式

## 参考资源
- [React 文档](https://react.dev/)
- [React Router 文档](https://reactrouter.com/)
- [Zustand 文档](https://github.com/pmndrs/zustand)
- [Vite 文档](https://vitejs.dev/)

### ESLint 配置
```js
// eslint.config.js
import antfu from '@antfu/eslint-config'

export default antfu({
  // 启用 TypeScript 支持
  typescript: {
    tsconfigPath: 'tsconfig.json',
  },
  // 启用 React 支持
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