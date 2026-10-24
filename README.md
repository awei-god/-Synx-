# Synx 工作室招新提交

## 环境
- 操作系统：Windows 11
- 浏览器：Chrome / Edge
- 编辑器：VSCode

## 如何运行
直接用浏览器打开 `basic/frontend/index.html` 即可。

## 已完成
- Markdown 自我介绍
- C 语言全部题目
- 基础模块 A：校园活动展示页
  - 静态卡片、Flex 布局、分类标签
  - 动态生成卡片、点赞、查看更多/收起
  - 分类筛选
  - 添加活动表单 + 非空校验
  - 了解风险，未进行转义，后面再说

## 基础模块 A：附加思考

### 1. 刷新后数据丢失与 localStorage
用户点赞或添加新活动后，如果按F5刷新，页面会重新加载，数组会回到初始的5条，点赞状态和新增活动都会丢失，因为数据只存在内存里面

可以用浏览器的'localStorage'保存:
**localStorage	浏览器本地存储，数据保存在用户电脑上**
**.setItem(key, value)	存入一条数据，key 是键名，value 是字符串**
**"activities"	键名，自己起的，读取时要用同一个**
**JSON.stringify(activities)	把数组/对象转成 JSON 字符串**

ps:localStorage 只能存字符串，不能直接存数组或对象。

- 用 `localStorage.setItem("activities", JSON.stringify(activities))` 保存活动列表；
- 用 `localStorage.setItem("likedIds", JSON.stringify(likedIds))` 保存已点赞的活动；
- 页面加载时用 `localStorage.getItem` 读取，`JSON.parse` 还原成数组；
- 每次点赞或添加活动后重新保存一次。

这样刷新后数据还在

### 2. 直接拼接用户输入的安全风险
(以下是AI回答，我不太清楚这个问题答案)

用户输入 `<img src=x onerror="alert('xss')">` 时，浏览器会把它当成真正的 HTML 执行，可能弹出弹窗、窃取信息，这就是 XSS（跨站脚本攻击）。

## 进阶大题一：任务看板
- 三列布局
- 初始四个任务，优先级颜色区分
- 状态流转：开始/完成/移走
- 删除任务+确认框
- 添加任务表单
- 搜索过滤：按标题或说明实时过滤

## 开放主观题
- 3.1 为什么学JS基础
- 3.2 AI辅助代码
- 3.3 想亲手做的项目
- 见`thinking/answers.md`


更安全的做法是用 `textContent` 插入文字：p.textContent = userInput;

## 未完成 / 遇到困难
- 基础模块 A 的 XSS 转义防护未实现，只做了理解，知道应该用 `textContent` 或转义函数。
- 进阶看板的搜索防抖、深色模式未做。
- 拖拽移动卡片未做。
- 任务看板数据未持久化，刷新后回到初始 4 条。

## AI 使用说明
- 使用 AI 辅助理解概念、排查报错、检查代码。
- 所有 AI 给出的代码都经过自己运行验证，能解释主要逻辑。
- 3.2 中记录了 AI 代码审查的完整过程。


## 参考来源
- MDN Web Docs
- 菜鸟教程
- deepseek AI 辅助