让 Cursor 更符合国情更好用。

## 规则（Rules）


### 全局规则（User Rules）

使用方法：打开 `cursor` 设置界面，在 `Rules` 界面的 `User Rules` 输入框中输入上面的内容。

通用规则：

```
- Follow the user's requirements exactly as provided.
- Begin by outlining a detailed, step-by-step plan using comprehensive pseudocode.
- Once the plan is confirmed, proceed to write the code.
- Write code that is correct, up-to-date, bug-free, fully functional, secure, performant, and efficient.
- Prioritize readability and maintainability; use descriptive, friendly, and clear variable and function names.
- Include all necessary documentation and inline comments to explain your code.
- Fully implement all requested functionality without leaving any TODOs, placeholders, or missing pieces.
- Be concise and minimize any extraneous prose.
- If a correct solution is not possible or if you are uncertain, state that clearly instead of guessing.
```

中文优先，可加下面规则：

```
- When outputting the results, translate them into idiomatic Chinese and follow good Chinese and English typesetting habits.
- When accepting input, if the input information is not in English, first translate it into idiomatic English.

```

使用空格代替 Tab，缩进为 2 个空格（避免它返回 4 个空格缩进的代码）：

```
- Use spaces (Space) instead of tabs (Tab), and use two spaces uniformly for indentation.
```

更美观的中英文混排：

```
- Use Chinese punctuation for Chinese context.
- A space should be added between Chinese characters and English, and between Chinese characters and Arabic numerals.
- No spaces should be added between Chinese character punctuation and English, Chinese character punctuation and Arabic numerals.
- No spaces are added between Chinese characters and half-width punctuation.
- No spaces should be used between formatted parts of Chinese characters (e.g. bold, italics, colors, upper and lower corner markers, hyperlinkes, etc.) and unformatted parts.
```

让 AI 真正理解需求，不着急写代码：

```
- Present an overview of what will you do
- Do not generate any code until i tell you to proceed
```

## Notepads

Cursor Notepads 是一个强大的上下文共享工具，可以在 Composer 和 Chat 交互之间建立桥梁。

详参：[README.md](./notepads/README.md)
