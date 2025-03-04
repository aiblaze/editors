# Vue 项目模板

## 项目初始化

### 使用 create-vue 创建项目
```bash
pnpm create vue@latest
```

### 推荐的项目配置
- TypeScript: Yes
- JSX: Yes
- Vue Router: Yes
- Pinia: Yes
- Vitest: Yes
- End-to-End Testing: Yes
- ESLint: Yes
- Prettier: Yes

## 项目结构
```
src/
├── assets/          # 静态资源
├── components/      # 可复用组件
│   ├── common/     # 通用组件
│   └── business/   # 业务组件
├── composables/     # 组合式函数
├── layouts/        # 布局组件
├── pages/          # 页面组件
├── router/         # 路由配置
├── stores/         # Pinia 状态管理
├── styles/         # 样式文件
├── types/          # TypeScript 类型
└── utils/          # 工具函数
```

## 开发规范

### 组件命名
- 文件名：PascalCase（如 `UserProfile.vue`）
- 组件名：PascalCase（如 `UserProfile`）
- 基础组件：以 Base 开头（如 `BaseButton.vue`）
- 单例组件：以 The 开头（如 `TheHeader.vue`）

### 组件结构
```vue
<script setup lang="ts">
// 1. 导入
import { ref, onMounted } from 'vue'
import type { PropType } from 'vue'

// 2. 类型定义
interface Props {
  title: string
  items?: string[]
}

// 3. Props 定义
const props = defineProps<Props>()

// 4. Emits 定义
const emit = defineEmits<{
  (e: 'update', value: string): void
}>()

// 5. 响应式数据
const count = ref(0)

// 6. 计算属性
const doubleCount = computed(() => count.value * 2)

// 7. 方法
const increment = () => {
  count.value++
}

// 8. 生命周期钩子
onMounted(() => {
  // 初始化逻辑
})
</script>

<template>
  <div class="component-name">
    <!-- 模板内容 -->
  </div>
</template>

<style scoped>
/* 样式内容 */
</style>
```

### 状态管理
- 使用 Pinia 进行状态管理
- 按功能模块拆分 store
- 使用组合式 API 风格
- 保持 store 的单一职责

### 路由配置
- 使用路由懒加载
- 实现路由守卫
- 统一的路由元信息
- 路由权限控制

### 样式规范
- 使用 SCSS 预处理器
- 采用 BEM 命名规范
- 使用 CSS 变量管理主题
- 响应式设计

### API 调用
- 使用 Axios 进行 HTTP 请求
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
- 组件测试：Vue Test Utils
- E2E 测试：Cypress
- 测试覆盖率要求

## 开发工具

### 推荐 VSCode 插件
- Volar
- TypeScript Vue Plugin
- ESLint
- Prettier
- GitLens

### 推荐浏览器插件
- Vue.js devtools
- Vue Performance Devtools

## 部署配置

### 构建优化
- 代码分割
- Tree Shaking
- 压缩优化
- CDN 配置

### 环境变量
```env
VITE_API_BASE_URL=http://api.example.com
VITE_APP_TITLE=My Vue App
```

## 常见问题解决

### 1. 组件通信
- Props 向下传递数据
- Emit 向上传递事件
- Provide/Inject 跨层级通信
- Pinia 全局状态管理

### 2. 性能优化
- 使用 `v-show` 代替频繁切换的 `v-if`
- 使用 `v-memo` 缓存不变化的模板
- 合理使用 `computed` 和 `watch`
- 避免不必要的组件重渲染

### 3. 类型安全
- 使用 TypeScript 类型注解
- 定义接口和类型
- 使用类型断言
- 启用严格模式

## 参考资源
- [Vue 3 文档](https://vuejs.org/)
- [Vue Router 文档](https://router.vuejs.org/)
- [Pinia 文档](https://pinia.vuejs.org/)
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
  // 启用 Vue 支持
  vue: true,
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