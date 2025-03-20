# 代码风格指南

## 代码缩进规范

### 基本原则
- 使用空格（Space）而不是制表符（Tab）进行缩进
- 缩进统一使用 2 个空格
- 保持一致的缩进风格

### 不同语言的缩进规范

#### JavaScript/TypeScript
```typescript
// 函数缩进
function example() {
  const result = {
    name: 'test',
    value: 42,
  }
  return result
}

// 条件语句缩进
if (condition) {
  // 代码块
} else {
  // 代码块
}

// 循环语句缩进
for (let i = 0; i < 10; i++) {
  // 代码块
}

// 链式调用缩进
const result = someFunction()
  .then(data => {
    return processData(data)
  })
  .catch(error => {
    console.error(error)
  })
```

#### HTML
```html
<div class="container">
  <header class="header">
    <nav class="nav">
      <a href="#" class="nav-link">首页</a>
      <a href="#" class="nav-link">关于</a>
    </nav>
  </header>
  <main class="main">
    <article class="article">
      <h1 class="title">标题</h1>
      <p class="content">内容</p>
    </article>
  </main>
</div>
```

#### CSS/SCSS
```scss
.component {
  &__header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem;
    
    &-title {
      font-size: 1.5rem;
      font-weight: bold;
    }
  }
  
  &__content {
    margin: 1rem 0;
    
    &-item {
      padding: 0.5rem;
      border-bottom: 1px solid #eee;
      
      &:last-child {
        border-bottom: none;
      }
    }
  }
}
```

## 中英文排版规范

### 基本原则
- 中文与英文之间需要加空格
- 中文与数字之间需要加空格
- 中文与标点符号之间不加空格
- 英文与标点符号之间不加空格

### 示例

#### 正确示例
- 使用 `npm install` 安装依赖
- 运行 `yarn dev` 启动开发服务器
- 在 `src/components` 目录下创建组件
- 这是一个 React 组件
- 版本号为 1.0.0
- 使用 ESLint 进行代码检查

#### 错误示例
- 使用`npm install`安装依赖
- 运行`yarn dev`启动开发服务器
- 在`src/components`目录下创建组件
- 这是一个React组件
- 版本号为1.0.0
- 使用ESLint进行代码检查

### 特殊情况

#### 代码块
- 代码块内的中英文之间不需要加空格
- 代码注释中的中英文之间需要加空格

```typescript
// 正确的注释格式
const name = 'test' // 这是一个测试变量

// 错误的注释格式
const name = 'test' //这是一个测试变量
```

#### 变量名和函数名
- 变量名和函数名中的中英文之间不需要加空格
- 使用驼峰命名法

```typescript
// 正确的命名
const userName = 'test'
const userInfo = {
  firstName: 'John',
  lastName: 'Doe'
}

// 错误的命名
const user_name = 'test'
const user_info = {
  first_name: 'John',
  last_name: 'Doe'
}
```

#### 文档注释
- JSDoc 注释中的中英文之间需要加空格

```typescript
/**
 * 这是一个测试函数
 * @param {string} name - 用户名称
 * @returns {string} 处理后的名称
 */
function processName(name: string): string {
  return name.trim()
}
```

### 工具配置

#### ESLint 配置
```js
// eslint.config.js
import antfu from '@antfu/eslint-config'

export default antfu({
  // 启用 TypeScript 支持
  typescript: {
    tsconfigPath: 'tsconfig.json',
  },
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

#### VSCode 配置
```json
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": false,
  "files.insertFinalNewline": true,
  "files.trimTrailingWhitespace": true
}
```

## 参考资源
- [antfu/eslint-config](https://github.com/antfu/eslint-config)
- [中文文案排版指北](https://github.com/sparanoid/chinese-copywriting-guidelines)
- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html) 