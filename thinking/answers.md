# 开放主观题
## 3.1
**AI 时代，我们为什么还要扎实学习编程基础？结合本次做题经历，写一写你的思考。**

说真的，在学完这次前端设计开发版块的题目过后，我感到很深的无力感，我觉得AI实在过于强大，我甚至不需要给它优质的关键词，它就已经可以给我整个周期的学习计划以及所有题目的完整的答案，而且做出来的质量非常高。

前端的编程基础确实非常有趣，它不复杂，组合起来的逻辑很让我着迷（为了研究如何让看板项目流动而找了许多攻略）。但是我自己打出的代码始终不能让我满意，AI给我的代码更简略以及更具备可读性。在检查报错节点上，AI的效率过于夸张与直接，我一度觉得前端真的可能不再需要人来给框架，人要做的只是给予关键词，以及设计方面对于CSS的需求。

理解完一些难度较大的函数后，我发现AI给予的函数弯子绕的很大但是十分简洁，我不太明白学习基础的意义是什么了。

## 3.2

### 我选的代码

我选的是任务看板里面的`bindTaskEvents`函数：

 function bindTaskEvents(){
        document.querySelectorAll(".task-card").forEach(function(card){
            const taskId = Number(card.dataset.id);

            const actionBtn = card.querySelector('[data-action="next"], [data-action="back"]');
            if(actionBtn){
                actionBtn.addEventListener("click", function(){
                    changeStatus(taskId, actionBtn.dataset.action);
                });
            }

            const deleteBtn = card.querySelector('[data-action="delete"]');
            deleteBtn.addEventListener("click", function(){
                deleteTask(taskId);
            });
        });
    }

### 我给AI的提示词

“这是我写的一个任务看板的按钮事件绑定函数。每张卡片有流转按钮和删除按钮，卡片会随着任务状态变化重新渲染。请重点检查：1. 有没有潜在的边界错误；2. 事件绑定会不会重复；3. 代码风格有没有问题。”

### AI给的建议
1. `deleteBtn` 没有判空，如果某张卡片没有删除按钮会报错。
2. `querySelectorAll(".task-card")` 每次重新渲染后都会重新绑定，如果 `renderBoard` 被调用两次，事件会绑两次。
3. 建议把 `[data-action="next"], [data-action="back"]` 拆成两个独立查询，可读性更好。

### 我的判断
部分采纳。我检查了代码，`renderBoard` 只在一个地方调用，且每次都用 `innerHTML` 重建卡片，旧事件会随旧 DOM 销毁，不会重复绑定。所以没有改，但在 README 里记了一笔。

### 修改后的

 const deleteBtn = card.querySelector('[data-action="delete"]');
    if(deleteBtn){
        deleteBtn.addEventListener("click", function(){
            deleteTask(taskId);
        });
    }

## 3.3 小项目
### 项目想法
我想做一个“桌面挂机小游戏”：游戏画面不放在浏览器标签页里，而是直接显示在电脑桌面上，像一个小挂件或悬浮窗，能直接在桌面上查看资源、点击升级、领取收益。

### 解决的问题

解决上班族与码农的无聊

### 大概需要：
- 游戏画面：资源数量、产出速度、升级按钮、离线收益提示；
- 游戏逻辑：用 JS 定时器每秒增加资源，记录上次关闭时间，计算离线收益；
- 存档：先用 localStorage 存进度，刷新或重启不丢；
- 桌面显示：这是我最想学的部分，可能的方向有：
  - 用 Electron 或 Tauri 把网页打包成桌面应用，做一个透明/无边框的小窗口；
  - 或者做成桌面小组件/悬浮窗，贴在桌面上；
  - 或者作为动态壁纸运行；
- 以及：简单的数值平衡、成就、音效。

### 要学的：

- 更熟练地使用 localStorage 和 JSON，保存游戏进度；
- 学 `setInterval` 和 `Date`，做定时产出和离线时间计算；
- 学 Electron 或 Tauri，理解网页怎么变成桌面应用、怎么做透明窗口和置顶；
- 了解桌面小组件或动态壁纸的运行方式；
- 学一点数值设计，让游戏前期不无聊、后期不崩。

### 和本次招新题的关系
基础模块 A 做了动态渲染、localStorage 保存、添加和筛选，这些正好是挂机游戏界面的基础。任务看板让我理解了“数据驱动渲染”：改数据、重新渲染。挂机游戏也是同一个思路——资源数据每秒变化，页面跟着更新。先把这两块练熟，再去做桌面挂机游戏会顺很多。

