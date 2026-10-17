# HTML 属性
## 基本语法
`<开始标签 属性名=“属性值”>`

1. 每个HTML元素可以具有不同的属性
```html
<p id="describe" class="section">这是一个标签段落</p>
<a href="https://baidu.com">这是一个超链接</a>
```
2. 属性名称不区分大小写，属性值对大小写敏感
```html
<img src="example.jpg" alt="">
<img SRC="example.jpg" alt="">
<img src="EXAMPLE.jpg" alt="">
<!---->
<!--前两者相同，第三个与前两个不一样-->
```

## 适用于大多数HTML元素的属性
|属性|描述|
|:----:|:----:|
|class|为HTML元素定义一个或多个类名（类名从样式文件引入）|
|id|定义元素唯一的id|
|style|规定元素的行内样式|

# HTML 属性知识点整理

> 属性用于为 HTML 元素提供附加信息，写在开始标签内，形式为 `名="值"`。

## 一、基本语法

```html
<标签名 属性名="属性值" 属性名2='属性值2' 布尔属性>
```

### 规则

- 属性写在**开始标签**或自闭合标签中。
- 属性名在 HTML 中**不区分大小写**，但推荐全小写。
- 属性值推荐用**双引号**，也可用单引号。
- 值中不含空格、引号、`=`、`<`、`>` 时可省略引号，但不推荐。
- 属性顺序无关。
- 同一元素不应出现重复属性；重复时解析器通常保留第一个。
- 属性值中若含引号，使用实体：`&quot;`、`&#39;`。
- 空值合法，例如 `alt=""`、`value=""`。

---

## 二、属性分类

| 分类 | 说明 | 示例 |
|---|---|---|
| 全局属性 | 几乎所有元素都可用 | `id`、`class`、`style`、`title` |
| 元素专属属性 | 只对特定元素有意义 | `href`、`src`、`colspan` |
| 布尔属性 | 存在即为真，省略即为假 | `disabled`、`checked` |
| 自定义数据属性 | 开发者自定义数据 | `data-id`、`data-role` |
| 事件属性 | 绑定 JS 事件 | `onclick`、`onchange` |
| ARIA 属性 | 无障碍语义 | `role`、`aria-label` |

---

## 三、全局属性

| 属性 | 说明 | 示例 |
|---|---|---|
| `id` | 元素唯一标识，页面中应唯一 | `id="app"` |
| `class` | 类名，可多个，空格分隔 | `class="btn primary"` |
| `style` | 内联样式 | `style="color: red"` |
| `title` | 鼠标悬停提示 | `title="提示文字"` |
| `lang` | 元素语言 | `lang="zh-CN"` |
| `dir` | 文本方向 | `dir="rtl"` |
| `hidden` | 隐藏元素 | `hidden` |
| `tabindex` | Tab 键顺序 | `tabindex="0"` |
| `accesskey` | 快捷键 | `accesskey="s"` |
| `contenteditable` | 是否可编辑 | `contenteditable="true"` |
| `draggable` | 是否可拖拽 | `draggable="true"` |
| `spellcheck` | 拼写检查 | `spellcheck="false"` |
| `translate` | 是否翻译 | `translate="no"` |
| `data-*` | 自定义数据 | `data-id="1"` |
| `role` | ARIA 角色 | `role="button"` |
| `aria-*` | 无障碍属性 | `aria-label="关闭"` |
| `inert` | 惰性，不可交互 | `inert` |
| `popover` | 弹出层 | `popover` |
| `autocapitalize` | 自动大写 | `autocapitalize="off"` |
| `inputmode` | 输入模式 | `inputmode="numeric"` |

---

## 四、常用元素专属属性

### 1. 超链接 `<a>`

| 属性 | 说明 |
|---|---|
| `href` | 目标 URL |
| `target` | 打开方式 |
| `rel` | 链接与当前文档关系 |
| `download` | 下载而非跳转 |
| `hreflang` | 目标语言 |
| `type` | 目标 MIME 类型 |
| `referrerpolicy` | Referer 策略 |

`target` 常用值：

| 值 | 说明 |
|---|---|
| `_self` | 当前窗口/标签 |
| `_blank` | 新窗口/标签 |
| `_parent` | 父框架 |
| `_top` | 顶层框架 |
| 自定义名称 | 指定浏览上下文 |

新标签页打开外部链接推荐：

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">示例</a>
```

### 2. 图片 `<img>`

| 属性 | 说明 |
|---|---|
| `src` | 图片地址，必须是图片直链 |
| `alt` | 替代文本，图片无法显示时显示 |
| `width` | 宽度 |
| `height` | 高度 |
| `srcset` | 响应式图片候选 |
| `sizes` | 响应式图片尺寸 |
| `loading` | `lazy` 懒加载 |
| `decoding` | `sync` / `async` / `auto` |
| `crossorigin` | 跨域设置 |
| `referrerpolicy` | Referer 策略 |
| `usemap` | 图像映射 |
| `ismap` | 服务器端图像映射 |

示例：

```html
<img
  src="small.jpg"
  srcset="small.jpg 480w, medium.jpg 800w, large.jpg 1200w"
  sizes="(max-width: 600px) 480px, 800px"
  alt="示例图片"
  loading="lazy"
  decoding="async"
>
```

### 3. 表单 `<form>`

| 属性 | 说明 |
|---|---|
| `action` | 提交地址 |
| `method` | `get` / `post` |
| `enctype` | 编码类型 |
| `target` | 提交目标 |
| `name` | 表单名称 |
| `autocomplete` | 自动完成 |
| `novalidate` | 跳过验证 |
| `accept-charset` | 字符编码 |

`enctype` 常用值：

| 值 | 说明 |
|---|---|
| `application/x-www-form-urlencoded` | 默认 |
| `multipart/form-data` | 文件上传 |
| `text/plain` | 纯文本 |

### 4. 输入 `<input>`

| 属性 | 说明 |
|---|---|
| `type` | 输入类型 |
| `name` | 提交字段名 |
| `value` | 初始值 |
| `placeholder` | 占位提示 |
| `required` | 必填 |
| `disabled` | 禁用 |
| `readonly` | 只读 |
| `checked` | 默认选中 |
| `maxlength` | 最大长度 |
| `minlength` | 最小长度 |
| `pattern` | 正则验证 |
| `min` / `max` | 最小/最大值 |
| `step` | 步长 |
| `multiple` | 允许多选 |
| `accept` | 文件类型 |
| `autocomplete` | 自动完成 |
| `list` | 关联 datalist |
| `form` | 关联表单 |
| `size` | 宽度 |

常见 `type`：

`text`、`password`、`email`、`url`、`tel`、`number`、`range`、`date`、`time`、`datetime-local`、`month`、`week`、`color`、`checkbox`、`radio`、`file`、`hidden`、`submit`、`reset`、`button`、`search`。

### 5. 按钮 `<button>`

| 属性 | 说明 |
|---|---|
| `type` | `submit` / `reset` / `button` |
| `name` | 名称 |
| `value` | 值 |
| `disabled` | 禁用 |
| `form` | 关联表单 |
| `formaction` | 覆盖提交地址 |
| `formmethod` | 覆盖提交方法 |
| `formnovalidate` | 覆盖验证 |
| `formtarget` | 覆盖提交目标 |

### 6. 元信息 `<meta>`

| 属性 | 说明 |
|---|---|
| `charset` | 字符编码 |
| `name` | 元信息名 |
| `content` | 元信息内容 |
| `http-equiv` | HTTP 等效头 |
| `property` | Open Graph 等 |

示例：

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="页面描述">
<meta http-equiv="refresh" content="5;url=https://example.com">
```

### 7. 外部资源 `<link>`

| 属性 | 说明 |
|---|---|
| `rel` | 关系 |
| `href` | 资源地址 |
| `type` | MIME 类型 |
| `media` | 媒体查询 |
| `as` | 预加载类型 |
| `crossorigin` | 跨域 |
| `integrity` | 子资源完整性 |
| `hreflang` | 语言 |
| `sizes` | 图标尺寸 |

### 8. 脚本 `<script>`

| 属性 | 说明 |
|---|---|
| `src` | 脚本地址 |
| `async` | 异步加载，立即执行 |
| `defer` | 延迟到文档解析后执行 |
| `type` | 脚本类型 |
| `nomodule` | 不支持模块时执行 |
| `crossorigin` | 跨域 |
| `integrity` | 完整性校验 |
| `referrerpolicy` | Referer 策略 |

### 9. 表格相关

| 元素 | 属性 |
|---|---|
| `<td>` / `<th>` | `colspan`、`rowspan`、`headers` |
| `<th>` | `scope`、`abbr` |
| `<col>` | `span` |
| `<colgroup>` | `span` |

### 10. 媒体 `<video>` / `<audio>`

| 属性 | 说明 |
|---|---|
| `src` | 媒体地址 |
| `controls` | 显示控制条 |
| `autoplay` | 自动播放 |
| `loop` | 循环 |
| `muted` | 静音 |
| `poster` | 视频封面 |
| `preload` | 预加载策略 |
| `playsinline` | 行内播放 |
| `width` / `height` | 尺寸 |
| `crossorigin` | 跨域 |

---

## 五、布尔属性

布尔属性只要**出现**就表示 `true`，省略表示 `false`。

常见布尔属性：

`allowfullscreen`、`async`、`autofocus`、`autoplay`、`checked`、`controls`、`default`、`defer`、`disabled`、`formnovalidate`、`hidden`、`inert`、`ismap`、`itemscope`、`loop`、`multiple`、`muted`、`nomodule`、`novalidate`、`open`、`readonly`、`required`、`reversed`、`selected`、`playsinline`。

正确写法：

```html
<input type="checkbox" checked>
<input type="text" disabled>
<select multiple>
  <option selected>选项</option>
</select>
```

错误理解：

```html
<!-- 仍然表示禁用，因为布尔属性存在即为 true -->
<input type="text" disabled="false">
```

---

## 六、自定义数据属性 `data-*`

用于在元素上存储自定义数据。

```html
<div id="user" data-user-id="123" data-role="admin"></div>
```

JavaScript 通过 `dataset` 访问：

```js
const el = document.getElementById('user');

console.log(el.dataset.userId); // "123"
console.log(el.dataset.role);   // "admin"
```

规则：

- `data-` 后建议小写。
- 多个单词用连字符，如 `data-user-id`。
- JS 中转为驼峰：`dataset.userId`。
- 可用于 CSS 选择器：`[data-role="admin"]`。

---

## 七、事件属性

HTML 中可直接写事件属性，但现代开发推荐用 JS 绑定。

常见事件属性：

| 属性 | 触发时机 |
|---|---|
| `onclick` | 点击 |
| `ondblclick` | 双击 |
| `onmousedown` | 鼠标按下 |
| `onmouseup` | 鼠标松开 |
| `onmouseover` | 鼠标移入 |
| `onmouseout` | 鼠标移出 |
| `onmousemove` | 鼠标移动 |
| `onkeydown` | 键盘按下 |
| `onkeyup` | 键盘松开 |
| `oninput` | 输入时 |
| `onchange` | 值改变 |
| `onsubmit` | 表单提交 |
| `onreset` | 表单重置 |
| `onfocus` | 获得焦点 |
| `onblur` | 失去焦点 |
| `onload` | 加载完成 |
| `onerror` | 加载错误 |
| `onscroll` | 滚动 |
| `onresize` | 窗口尺寸变化 |

示例：

```html
<button onclick="alert('点击了')">按钮</button>
```

更推荐：

```html
<button id="btn">按钮</button>
<script>
  document.getElementById('btn').addEventListener('click', () => {
    alert('点击了');
  });
</script>
```

---

## 八、ARIA 属性

用于增强无障碍语义，但不能替代原生语义元素。

| 属性 | 说明 |
|---|---|
| `role` | 元素角色 |
| `aria-label` | 无障碍名称 |
| `aria-labelledby` | 通过其他元素命名 |
| `aria-describedby` | 描述信息 |
| `aria-hidden` | 是否对辅助技术隐藏 |
| `aria-expanded` | 是否展开 |
| `aria-controls` | 控制的目标元素 |
| `aria-live` | 动态内容播报 |
| `aria-current` | 当前项 |
| `aria-disabled` | 是否禁用 |
| `aria-checked` | 是否选中 |
| `aria-selected` | 是否选择 |

示例：

```html
<button aria-label="关闭弹窗">×</button>
```

---

## 九、属性 vs DOM Property

| 对比 | Attribute | Property |
|---|---|---|
| 所在位置 | HTML 标签上 | DOM 对象上 |
| 读写方式 | `getAttribute()` / `setAttribute()` | `.属性名` |
| 示例 | `input.getAttribute('value')` | `input.value` |
| 初始值/当前值 | 多为初始值 | 多为当前值 |
| 布尔属性 | 存在即 true | 通常为 true / false |

常见映射：

| Attribute | Property |
|---|---|
| `class` | `className` |
| `for` | `htmlFor` |
| `checked` | `checked` |
| `value` | `value` |

示例：

```html
<input id="name" value="初始值">
```

```js
const input = document.getElementById('name');

console.log(input.getAttribute('value')); // "初始值"
input.value = '新值';
console.log(input.value);                 // "新值"
console.log(input.getAttribute('value')); // "初始值"
```

---

## 十、常见易错点

| 易错点 | 正确做法 |
|---|---|
| `lang="zh=CN"` | `lang="zh-CN"` |
| `target="blank"` | `target="_blank"` |
| 图片 `src` 写搜索详情页 | 写图片直链 |
| 布尔属性写 `disabled="false"` | 要禁用写 `disabled`，不要写 `false` |
| `id` 重复 | `id` 应唯一 |
| 外部链接新标签页无安全设置 | 加 `rel="noopener noreferrer"` |
| `alt` 缺失 | 图片应有合适 `alt` |
| 表单控件无 `label` | 使用 `<label for="id">` 关联 |
| 用 `style` 写大量样式 | 优先外部 CSS |
| 用 `data-*` 代替语义类名 | 语义信息优先用合适元素和类 |

---

## 十一、修正示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <a href="https://www.baidu.com">这是一个超链接</a>
  <br>
  <a href="https://www.baidu.com" target="_blank" rel="noopener noreferrer">
    这是第二个超链接
  </a>
  <hr>
  <img src="图片直链.jpg" alt="图片描述">
</body>
</html>
```

---

## 十二、最佳实践

- 属性名小写，属性值加引号。
- 样式优先用 CSS，交互优先用 `addEventListener`。
- 图片必须有有意义的 `alt`；装饰图片可用 `alt=""`。
- 表单控件用 `label` 关联。
- 新标签页打开外部链接时加 `rel="noopener noreferrer"`。
- 自定义数据用 `data-*`，通过 `dataset` 访问。
- 无障碍优先使用原生语义元素，再考虑 ARIA。
- 不要依赖重复属性的解析行为。
- 布尔属性不要赋 `"false"`。


# CSS
CSS全名是Cascading Style Sheets,中文名层叠样式表
用于定义网页样式和布局的样式表语言
通过CSS，可以指定页面中的各个元素的颜色、字体、大小、间距、边距、背景等样式，从而实现更精确的页面设计

## 内边距和外边距
**内边距**和**外边距**是 CSS 盒模型里最容易混淆的两个概念，但一句话就能分清：

- **内边距 `padding`**：元素内容到边框之间的距离，属于元素**内部**。
- **外边距 `margin`**：元素边框到其他元素之间的距离，属于元素**外部**。

### 盒模型里的位置

一个元素的完整结构从内到外是：

```text
内容 content
  ↓
内边距 padding
  ↓
边框 border
  ↓
外边距 margin
```

也就是：

```text
margin
  border
    padding
      content
    padding
  border
margin
```

### 结合你前面的代码看

```css
div {
    padding: 20px;
    max-width: 400px;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}
```

这里的：

```css
padding: 20px;
```

意思是：`div` 里面的文字、图片等内容，距离 `div` 的边框有 20px。  
所以内容不会贴着边，看起来更舒服。

如果你再加一个：

```css
margin: 10px;
```

那就表示：这个 `div` 的边框外面，还要再留出 10px 的空隙，用来和其他元素隔开。

### 主要区别

| 对比项 | 内边距 `padding` | 外边距 `margin` |
|---|---|---|
| 位置 | 边框内部 | 边框外部 |
| 作用 | 让内容和边框之间有呼吸感 | 让元素和其他元素之间有距离 |
| 背景色 | 会被背景色覆盖 | 不会被背景色覆盖 |
| 点击区域 | 算在元素点击区域内 | 不算在元素点击区域内 |
| 能否为负值 | 不能 | 可以，负 margin 会让元素偏移或重叠 |
| 常见用途 | 按钮、卡片内部留白 | 元素间距、水平居中 |

### 简写规则

`padding` 和 `margin` 的简写规则一样：

```css
padding: 10px;
/* 上下左右都是 10px */

padding: 10px 20px;
/* 上下 10px，左右 20px */

padding: 10px 20px 30px;
/* 上 10px，左右 20px，下 30px */

padding: 10px 20px 30px 40px;
/* 上 10px，右 20px，下 30px，左 40px */
```

`margin` 同理：

```css
margin: 10px 20px 30px 40px;
```

### 一个常见用法

水平居中：

```css
div {
    width: 400px;
    margin: 0 auto;
}
```

这里的 `margin: 0 auto;` 表示上下外边距为 0，左右自动平分，所以元素会水平居中。

### 注意点

1. **`padding` 不能为负数**，写了负值不生效。
2. **`margin` 可以为负数**，会让元素往反方向移动，甚至重叠。
3. 相邻块级元素的上下 `margin` 有时会合并，这叫**外边距折叠**。
4. 如果设置了：

```css
box-sizing: border-box;
```

那么 `width` 会包含 `padding` 和 `border`，但**不包含 `margin`**。

### 记忆方法

- `padding`：内衬，像盒子里面塞的泡沫，保护内容不贴边。
- `margin`：隔壁距离，像两个盒子之间留的空隙。
- 背景色会铺到 `padding`，但不会铺到 `margin`。

总结：

> **内边距是内容到边框的距离，外边距是边框到外部的距离。**  
> `padding` 管内部留白，`margin` 管外部间距。
>
> # <script>
`<script>` 是 **HTML 标签**，作用是：

> 在网页中**嵌入 JavaScript 代码**，或者**引用外部 JavaScript 文件**。

它不是用来显示内容的，而是让浏览器加载并执行脚本。

## 1. 内联写法

直接把 JavaScript 写在标签里面：

```html
<script>
    console.log("Hello");
    alert("页面加载了");
</script>
```

浏览器解析到这里时，会执行里面的 JavaScript。

## 2. 外部引用

用 `src` 属性引入外部 `.js` 文件：

```html
<script src="app.js"></script>
```

注意：写了 `src` 后，标签中间一般不要再写代码：

```html
<script src="app.js">
    // 这里通常不会执行
</script>
```

正确写法是：

```html
<script src="app.js"></script>
```

## 3. 常见位置

### 放在 `<body>` 末尾

```html
<body>
    <div id="app"></div>
    <script src="app.js"></script>
</body>
```

好处是 HTML 先渲染，脚本再执行，能操作到前面的元素。

### 放在 `<head>` 里

```html
<head>
    <script src="app.js" defer></script>
</head>
```

建议加 `defer`，让脚本在 HTML 解析完成后再执行。

## 4. `defer` 和 `async`

```html
<script src="app.js" defer></script>
```

| 属性 | 作用 |
|---|---|
| `defer` | 异步下载，等 HTML 解析完再按顺序执行 |
| `async` | 异步下载，下载完立刻执行，不保证顺序 |
| 都不加 | 阻塞 HTML 解析，下载并执行完才继续 |

一般业务脚本用：

```html
<script src="app.js" defer></script>
```

独立统计脚本可以用：

```html
<script src="analytics.js" async></script>
```

## 5. `type="module"`

现代 JavaScript 模块写法：

```html
<script type="module" src="main.js"></script>
```

特点：

- 支持 `import` / `export`
- 默认延迟执行，类似 `defer`
- 模块作用域独立

## 6. 和 CSS 的区别

| 标签 | 作用 |
|---|---|
| `<style>` | 写 CSS 样式 |
| `<script>` | 写 JavaScript 脚本 |
| `<link rel="stylesheet">` | 引入外部 CSS |

## 7. 注意

- `<script>` 里的代码会被浏览器执行，不要随便插入不可信内容，否则有 XSS 风险。
- 脚本里可以用 `document.querySelector()` 操作页面元素。
- 如果脚本要操作 DOM，最好放在 `body` 末尾，或者加 `defer`。
- `<script>` 不会在页面上显示文字，除非脚本主动修改 DOM。

## 总结

> `<script>` 是 HTML 中用来写或引入 JavaScript 的标签。  
> 内联用标签包裹代码，外部用 `src` 引入文件。  
> 常配合 `defer`、`async` 或 `type="module"` 控制加载和执行方式。