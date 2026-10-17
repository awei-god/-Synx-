# <font face="仿宋" font color=black>Markdown入门教程</font>
## ***一. 常用语言***
 1. **标题**
#一级标题
##二级标题
###三级标题
...
 2. **引用**
> （在此编辑需要引用的内用）
>> 可以二级引用...
 3. **列表**
    1. 无序列表
    - 列表1
    + 列表2
    * 列表3
    2. 有序列表（与嵌套有关）
    3. 嵌套：就是在一个大标题下面套小标题时，先按tab键（打印四格）后对每一个小标题按大标题处理。Eg：5. 标题
    4. Todolist
    - [ ] 这个还挺麻烦，中文的中括号与英文的还不一样
    - [ ] 在预览右边可以点击那个空格，此时系统会自动编辑
    - [x] 例子
4. **表格**
   
    | 左对齐 | 居中对齐 | 右对齐 |
    | :---- | :----: | ----: |
    | 此冒号需用英文打出 | 这个横线无所谓几个，但必须有这个对齐符号，不然不认定为表格形式 | 且表格在嵌套标题中需要空一行表格才会显示出来
5. **段落**
    - 换行？--两个以上空格后回车/空一行  
  abc
  
    - 分割线--三个以上的星号（如果要分割线下方的无序列表与上方对齐，则在这几个星号前加上tab）
    ***
    - 字体
  
    | 字体 | 代码 |
    | :----: | :----: |
    | *斜体* | * * |
    | ==高亮== | == == |
    | **粗体** | ** ** |
    | ***斜粗体*** | *** *** |
    | ~~删除~~ | ~~ ~~ |
    | <u>下划线</u>| 左右两个<u> |
    - 脚注
    例如这个注脚[^1]
6. **代码**
   编辑一段代码用三个```将代码括起来
    ```
    #include<iostream>
    using namepace std;
    int main()
    {
        print("hello world");
    }    
    ```  
    编辑一句代码用一个括起来
    ` print("hello world"); `
7. **超链接**
    - [链接名称](链接地址)
    eg: [b站](https://www.bilibili.com/)
    - 或者，<链接地址>
    eg:<https://www.bilibili.com/>
8. **图片**
   - 本质上要用图床进行插入
    [一个免费图床](http://imgse.com/)
   - 使用markdown语法插入
    [![pZSaCCD.webp](https://s21.ax1x.com/2025/11/04/pZSaCCD.webp)](https://imgchr.com/i/pZSaCCD)
    - 使用html语言实现调整图片大小与位置功能:
  a. 在图床网站上直接粘贴图片过来后可以在border后面进行改长宽,
  b. 并且可以加入\<div
align=center>进行居中
<a href="https://imgchr.com/i/pZSaCCD"><div
align=center><img src="https://s21.ax1x.com/2025/11/04/pZSaCCD.webp" alt="pZSaCCD.webp" border="0" width="50%" height="50%" /></a>
## ***二. 其他语言
1. 插入latex公式
   - 行内显示公式: $f(x)=ax+b$
   - 块内显示公式: 
$$
\begin{Bmatrix}
a & b \\
c & d 
\end{Bmatrix}
$$
2. html/css语法
   - ctrl+shift+p搜索"Markdown Preview Enhanced: Customize CSS"在style中使用CSS语法该标题格式等
3. 个性化
4. 导出为pdf：右键进入网站后另存为即可
[^1]: 执行命令的冒号都需要用英文输入   
