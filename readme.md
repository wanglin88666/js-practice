# 前端学习笔记

> HTML + CSS 基础知识点整理（day01 - day07）
>
> 说明：本文按「概念 → 语法 → 注意点」重排，并修正了原笔记中的笔误（如 `aotoplay`、`dvi*3`、`ul()` 等）。
> 标记 🆕 的小节为**查漏后补充**的内容（2026-09-17）。

## 目录

- [一、HTML](#一html)
  - [1.1 标签基础](#11-标签基础)
  - [1.2 HTML 骨架](#12-html-骨架) 🆕
  - [1.3 标签关系](#13-标签关系)
  - [1.4 注释](#14-注释)
  - [1.5 标题标签](#15-标题标签)
  - [1.6 段落标签](#16-段落标签)
  - [1.7 换行与水平线](#17-换行与水平线)
  - [1.8 文本格式化标签](#18-文本格式化标签)
  - [1.9 图像标签](#19-图像标签)
  - [1.10 路径](#110-路径)
  - [1.11 超链接标签](#111-超链接标签)
  - [1.12 音视频标签](#112-音视频标签)
  - [1.13 列表](#113-列表)
  - [1.14 表格](#114-表格) 🆕
  - [1.15 表单](#115-表单) 🆕
  - [1.16 布局标签与字符实体](#116-布局标签与字符实体) 🆕
  - [1.17 HTML5 语义化标签](#117-html5-语义化标签) 🆕
- [二、CSS](#二css)
  - [2.1 引入方式](#21-引入方式)
  - [2.2 基础选择器](#22-基础选择器)
  - [2.3 盒子模型与字体文本样式](#23-盒子模型与字体文本样式) 🆕
  - [2.4 复合选择器](#24-复合选择器)
  - [2.5 伪类选择器](#25-伪类选择器)
  - [2.6 CSS 三大特性](#26-css-三大特性)
  - [2.7 Emmet 写法](#27-emmet-写法)
  - [2.8 背景属性](#28-背景属性)
  - [2.9 元素显示模式](#29-元素显示模式) 🆕
  - [2.10 更多选择器](#210-更多选择器) 🆕
  - [2.11 伪元素](#211-伪元素) 🆕
  - [2.12 常用装饰与溢出属性](#212-常用装饰与溢出属性) 🆕
- [下一步](#下一步)

---

## 一、HTML

### 1.1 标签基础

标签**成对出现**，中间包裹内容：

```html
<开始标签>内容</结束标签>
```

- 结束标签比开始标签多一个 `/`
- 少数标签是**单标签**（如 `<br>`、`<hr>`、`<img>`）

### 1.2 HTML 骨架

**完整骨架**（VSCode 输入 `!` + `Tab` 会自动生成）：

```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>网页标题</title>
  </head>
  <body>
    网页主体内容
  </body>
</html>
```

| 标签 | 作用 |
| --- | --- |
| `<!DOCTYPE html>` | 文档类型声明，告诉浏览器用 **HTML5** 标准解析（必须写在第一行） |
| `html` | 整个网页，`lang="zh-CN"` 声明网页主要语言（利于翻译和无障碍） |
| `head` | 网页头部（给浏览器 / 搜索引擎看） |
| `title` | 网页标题（显示在浏览器标签页） |
| `body` | 网页主体（给用户看） |

> 快捷方式：输入 `!` 后按 `Tab`（或 `Enter`）自动生成骨架。

#### 🆕 `<head>` 里必须知道的 meta 标签

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="网页的简短描述，80 字以内">
<meta name="keywords" content="关键词1,关键词2">
```

| 标签 | 作用 |
| --- | --- |
| `charset="UTF-8"` | 字符编码。**不写或写错 → 中文全是乱码**（问号 / 方框） |
| `name="viewport"` | 移动端视口。**不写 → 手机上页面会被整体缩小成一团** |
| `name="description"` | 网页描述，搜索结果里显示的那段文字 |
| `name="keywords"` | 搜索关键词（现在权重较低，但仍是规范写法） |

> `title` + `description` + `keywords` 合称 **SEO 三要素**（TDK），做上线页面必写。

### 1.3 标签关系

- **父子关系（嵌套）**：`<html>` 是 `<head>`、`<body>` 的父级
- **兄弟关系（并列）**：`<head>` 与 `<body>` 是兄弟

### 1.4 注释

```html
<!-- 这是注释，不会显示在页面上 -->
```

- 快捷键：`Ctrl + /` 添加 / 删除注释

### 1.5 标题标签

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<!-- ... 一直到 h6 -->
```

- `h1` 一个网页中**建议只用一次**（利于 SEO）
- `h2` ~ `h6` 没有使用限制

### 1.6 段落标签

```html
<p>这是一个段落</p>
```

- 双标签，**独占一行**
- 段落之间有默认空隙（自带 margin）

### 1.7 换行与水平线

| 标签 | 作用 | 类型 |
| --- | --- | --- |
| `<br>` | 换行 | 单标签 |
| `<hr>` | 水平分割线 | 单标签 |

### 1.8 文本格式化标签

| 标签 | 效果 | 说明 |
| --- | --- | --- |
| `strong` | **加粗** | 有语义，推荐使用 |
| `em` | *倾斜* | 有语义，推荐使用 |
| `ins` | 下划线 | |
| `del` | ~~删除线~~ | |

> 对应的无语义写法：`b`（加粗）、`i`（倾斜）、`u`（下划线）、`s`（删除线）。

### 1.9 图像标签

```html
<img src="./logo.png" alt="网站 Logo" title="鼠标悬停提示">
```

| 属性 | 作用 |
| --- | --- |
| `src` | 图片路径（**必须属性**） |
| `alt` | 图片加载失败时的替换文字 |
| `title` | 鼠标悬停时的提示文字 |
| `width` / `height` | 宽高（只写一个，另一个等比缩放） |

### 1.10 路径

**相对路径**（从当前文件出发）：

| 写法 | 含义 |
| --- | --- |
| `.` | 当前目录 |
| `..` | 上一级目录 |
| `/` | 进入某个文件夹 |

**绝对路径**：

- Windows：从盘符出发，如 `D:\xuexi\images\a.png`
- Mac / Linux：从 `/` 出发
- 网络图片：直接写在线网址（注意友情链接 / 防盗链问题）

### 1.11 超链接标签

```html
<a href="https://www.baidu.com" target="_blank">百度</a>
```

| 属性 / 属性值 | 说明 |
| --- | --- |
| `href` | 跳转地址（**必须属性**） |
| `href="网址"` | 跳转外部网站 |
| `href="./a.html"` | 跳转本地文件（相对路径） |
| `href="#"` | 空链接，点击不跳转（开发占位用） |
| `target="_blank"` | 保留原网页，**新窗口**打开 |
| `target="_self"` | 当前窗口打开（默认） |

### 1.12 音视频标签

```html
<audio src="./music.mp3" controls loop></audio>

<video src="./video.mp4" controls muted autoplay loop></video>
```

| 属性 | 说明 |
| --- | --- |
| `controls` | 显示播放控制面板 |
| `loop` | 循环播放 |
| `muted` | 静音播放 |
| `autoplay` | 自动播放（**必须在静音状态下才生效**） |

> 属性名和属性值完全相同时，可以简写成属性名一个单词（如 `controls="controls"` → `controls`）。

### 1.13 列表

#### 无序列表

```html
<ul>
  <li>第一项</li>
  <li>第二项</li>
</ul>
```

- `ul` 里面**只能**包裹 `li`，`li` 里面可以包裹任何内容

#### 有序列表

```html
<ol>
  <li>第一步</li>
  <li>第二步</li>
</ol>
```

- 规则同无序列表

#### 定义列表

```html
<dl>
  <dt>标题</dt>
  <dd>详情说明</dd>
</dl>
```

- `dl` 只能包含 `dt` 和 `dd`
- `dt`（标题）、`dd`（详情）内部可以包含任何内容

### 1.14 表格

```html
<table border="1">
  <tr>
    <th>表头单元格</th>
    <td>内容单元格</td>
  </tr>
</table>
```

- 结构：`table` 嵌套 `tr`（行），`tr` 嵌套 `td` / `th`（单元格）
- `border` 给表格添加边框线（实际开发用 CSS 设置）

**结构标签**（可省略，但写上去语义更清晰）：

| 标签 | 含义 |
| --- | --- |
| `thead` | 表格头部 |
| `tbody` | 主要内容 |
| `tfoot` | 汇总信息 |

**合并单元格**：

| 类型 | 做法 |
| --- | --- |
| 跨行合并 | 保留**最上面**的单元格，加 `rowspan="n"` |
| 跨列合并 | 保留**最左边**的单元格，加 `colspan="n"` |

> 注意：**不能跨结构合并**（thead / tbody / tfoot 之间不能合并）。

#### 🆕 表格标题

```html
<table>
  <caption>学生成绩表</caption>
  <tr><th>姓名</th><th>分数</th></tr>
</table>
```

- `<caption>` 是表格的**大标题**，必须紧跟在 `<table>` 后面，默认在表格正上方居中。

### 1.15 表单

用于登录、注册、收集用户信息。

#### 🆕 form 表单标签

```html
<form action="/login" method="post">
  <!-- 表单控件写在这里 -->
</form>
```

| 属性 | 说明 |
| --- | --- |
| `action` | 数据提交到的后台地址 |
| `method` | 提交方式：`get`（默认，数据拼在网址后面）/ `post`（数据在请求体里，更安全） |
| `name` | 表单控件的**名称**，后台靠它取数据。所有要提交的控件都必须写 `name` |

> 笔记前面提到的 `name`（单选框分组）只是它的一个用法，`name` 更重要的作用是**作为提交数据的字段名**。

#### input 标签

```html
<input type="text" placeholder="请输入用户名">
```

| `type` 值 | 效果 |
| --- | --- |
| `text` | 文本框 |
| `password` | 密码框 |
| `radio` | 单选框 |
| `checkbox` | 多选框 |
| `file` | 上传文件 |

#### 🆕 HTML5 新增 type 值

| `type` 值 | 效果 |
| --- | --- |
| `email` | 邮箱框，提交时自动校验格式 |
| `number` | 数字框，只能输入数字 |
| `date` / `time` | 日期 / 时间选择器 |
| `search` | 搜索框 |
| `range` | 滑动条 |
| `color` | 取色器 |

- `placeholder="..."`：占位提示文本
- `name` 属性：单选框**必须有相同的 `name` 才能实现单选**
- `checked`：单选框 / 多选框默认选中
- `multiple`：上传文件时可以多选

#### 下拉菜单

```html
<select>
  <option>北京</option>
  <option selected>上海</option>
</select>
```

- `select` 是整体，`option` 是每一项
- `selected` 表示默认选中项

#### 文本域

```html
<textarea>默认文字</textarea>
```

- 双标签，用于发布评论、微博等多行输入
- 尺寸用 CSS 设置（禁用右下角拖拽：`resize: none`）

#### label 标签

绑定文字和表单控件，**增大点击范围**（点文字也能选中控件）：

```html
<!-- 写法一：for 对应 id -->
<input type="radio" id="man" name="sex">
<label for="man">男</label>

<!-- 写法二：直接包裹 -->
<label><input type="radio" name="sex">女</label>
```

#### 按钮

```html
<button type="submit">提交</button>
```

| `type` 值 | 说明 |
| --- | --- |
| `submit` | 提交按钮，可提交数据到后台 |
| `reset` | 重置按钮，清空表单 |
| `button` | 普通按钮，配合 JS 使用 |

> 在 `form` 表单中省略 `type` 属性，默认功能也是**提交**。

#### 🆕 表单控件常用属性

| 属性 | 作用 |
| --- | --- |
| `required` | 必填项，不填无法提交 |
| `disabled` | 禁用（变灰，不能点，**数据不会提交**） |
| `readonly` | 只读（能看能聚焦，但不能改，**数据会提交**） |
| `autofocus` | 页面加载后自动聚焦到该输入框 |
| `maxlength` | 最多可输入的字符数 |
| `value` | 控件的值 / 按钮上的文字 |

> `disabled` 和 `readonly` 长得很像，区别记住一句：**disabled 彻底不参与提交**。

### 1.16 布局标签与字符实体

```html
<div>块级元素，独占一行</div>
<span>行内元素，不换行</span>
```

常用字符实体：

| 显示结果 | 实体名称 |
| --- | --- |
| 空格 | `&nbsp;` |
| `<` | `&lt;` |
| `>` | `&gt;` |
| `&`（和号）🆕 | `&amp;` |
| `©` 版权 🆕 | `&copy;` |
| `¥` 人民币 🆕 | `&yen;` |

> 注意分号必须是**半角** `;`，写成中文全角 `；` 实体不会生效——这是原笔记里的错误。

### 1.17 HTML5 语义化标签

🆕 用 `div` 能搭出整个页面，但写出来的都是"无意义的盒子"。HTML5 提供了一组**有语义**的布局标签：

```html
<header>网页头部（Logo、导航）</header>
<nav>导航栏</nav>
<main>页面主要内容（一个页面只能有一个）</main>
<section>内容区块</section>
<article>独立文章 / 帖子</article>
<aside>侧边栏</aside>
<footer>网页底部（版权、备案信息）</footer>
```

| 标签 | 含义 |
| --- | --- |
| `header` | 头部 |
| `nav` | 导航 |
| `main` | 主体内容（页面中唯一） |
| `section` | 区块 |
| `article` | 独立文章内容 |
| `aside` | 侧边栏 |
| `footer` | 底部 |

**为什么要用它，而不是全用 div：**

1. **对搜索引擎友好（SEO）**：爬虫能看懂页面结构，有利于排名
2. **对无障碍友好**：屏幕阅读器可以识别，方便视障用户
3. **代码可读性好**：别人看一眼就知道哪块是导航、哪块是正文

> 表现上它们和 `div` 一样（都是块级元素，默认无样式），区别在**含义**。
> 从今天起练页面就养成习惯：`div` 只用在"没有更合适语义"的地方。

---

## 二、CSS

CSS 语法：**属性名和属性值成对出现**（键值对）。

```css
选择器 {
  属性名: 属性值;
}
```

### 2.1 引入方式

| 方式 | 写法 | 使用场景 |
| --- | --- | --- |
| 内部样式 | 写在 `<style>` 标签里 | 小练习、单页面 |
| 外部样式 | 单独 `.css` 文件，用 `<link>` 引入 | **开发中最常用** |
| 行内样式 | 写在标签的 `style` 属性里 | 配合 JavaScript 动态修改 |

```html
<link rel="stylesheet" href="./style.css">
```

### 2.2 基础选择器

#### 标签选择器

```css
p { color: red; }
```

用标签名做选择器，会选中**所有同名**标签。

#### 类选择器

```css
.red { color: red; }
```

```html
<div class="red">文字</div>
```

- 一个标签可以有**多个类名**：`class="red big"`

#### id 选择器

```css
#user { color: red; }
```

```html
<div id="user">文字</div>
```

- 同一个 `id` 在一个页面中**只能使用一次**
- 一般配合 JS 使用，很少用来设置 CSS

#### 通配符选择器

```css
* { margin: 0; padding: 0; }
```

自动查找页面**所有**标签，设置相同样式（常用于清除默认样式）。

### 2.3 盒子模型与字体文本样式

#### 盒子模型（🆕 补充完整）

**页面上所有元素都是一个矩形盒子**，由内到外四部分组成：

```
┌───────────── margin 外边距（盒子之间的距离）─────────────┐
│  ┌─────────── border 边框 ───────────┐                   │
│  │  ┌──── padding 内边距 ────┐       │                   │
│  │  │                        │       │                   │
│  │  │      content 内容      │       │                   │
│  │  │      (width/height)    │       │                   │
│  │  └────────────────────────┘       │                   │
│  └───────────────────────────────────┘                   │
└──────────────────────────────────────────────────────────┘
```

| 属性 | 说明 |
| --- | --- |
| `width` / `height` | 内容区宽高 |
| `padding` | 内边距，内容到边框的距离 |
| `border` | 边框 |
| `margin` | 外边距，盒子与盒子之间的距离 |
| `background-color` | 背景色（默认铺满 padding + content 区域） |

**简写规则（顺时针：上 右 下 左）**：

```css
padding: 10px;              /* 四个方向都是 10px */
padding: 10px 20px;         /* 上下 10px，左右 20px */
padding: 10px 20px 30px;    /* 上 10px，左右 20px，下 30px */
padding: 10px 20px 30px 40px; /* 上 右 下 左 */
```

`margin` 的简写规则完全相同，另外 `margin: 0 auto` 可以让**有宽度的块级盒子水平居中**。

**边框**：

```css
border: 1px solid #000;   /* 粗细 样式 颜色 */
border-radius: 8px;       /* 圆角 */
```

#### 🆕 box-sizing（必写）

```css
* {
  box-sizing: border-box;
}
```

| 值 | 盒子实际宽度 |
| --- | --- |
| `content-box`（默认） | `width + padding + border` → **加 padding 盒子会被撑大** |
| `border-box` | 就是设置的 `width`，padding 和 border 往里挤 |

> 新手 90% 的"布局算不对"都源于这个。**建议在每个项目开头就写上面那段代码**，一劳永逸。

#### 🆕 margin 的两个坑

1. **相邻兄弟元素的垂直 margin 会合并**：上下两个盒子分别是 20px 和 30px，实际间距是 **30px**（取大的），不是 50px。
2. **父子 margin 塌陷**：给子元素加 `margin-top`，结果父元素跟着一起往下掉。
   解决办法：给父元素加 `overflow: hidden`、或 `padding-top`、或 `border-top`。

#### 字体属性

| 属性 | 说明 |
| --- | --- |
| `font-size` | 字号大小，如 `16px`（浏览器默认 16px） |
| `font-weight` | 粗细：数字 `400` / `700` 或关键字 `normal` / `bold` |
| `font-style` | `normal` 正常，`italic` 倾斜 |
| `line-height` | 行高：`数字 + px` 或 `数字`（当前 font-size 的倍数） |
| `font-family` | 字体族，如 `font-family: 楷体, sans-serif` |

```css
/* 复合属性：倾斜 加粗 字号/行高 字体（必须写字号和字体） */
font: italic 700 20px/1.5 楷体;
```

> 单行文字垂直居中技巧：**行高 = 盒子高度**。

#### 文本属性

| 属性 | 说明 |
| --- | --- |
| `text-indent` | 首行缩进：`2em` = 缩进 2 个当前字号 |
| `text-align` | 内容对齐：`left`（默认）/ `center` / `right` |
| `text-decoration` | 修饰线：`none` / `underline` / `line-through` / `overline` |
| `color` | 文字颜色 |

**颜色表示法**：

```css
color: rgba(255, 0, 0, 0.5); /* r g b + 透明度 a（0~1） */
color: #ff0000;              /* 十六进制 */
color: #f00;                 /* 简写形式 */
```

### 2.4 复合选择器

由两个或多个基础选择器组合而成。

| 类型 | 写法 | 说明 |
| --- | --- | --- |
| 后代选择器 | `.father .son {}` | 空格隔开，选中**所有**后代 |
| 子代选择器 | `.father > .son {}` | `>` 隔开，只选**直接子级** |
| 并集选择器 | `div, p, span {}` | 逗号隔开，同时选中多组 |
| 交集选择器 | `p.box {}` | 紧挨着写，同时满足多个条件 |

### 2.5 伪类选择器

表示元素的**某种状态**。

```css
a:hover { color: red; }  /* 鼠标悬停 */
```

- 任何标签都可以设置 `:hover` 状态

**超链接的四个状态**（必须按下面顺序书写）：

| 伪类 | 时机 |
| --- | --- |
| `:link` | 访问前 |
| `:visited` | 访问后 |
| `:hover` | 鼠标悬停 |
| `:active` | 点击时 |

> 记忆口诀：**LVHA**（love & hate）。

### 2.6 CSS 三大特性

#### 继承性

- 子级默认继承父级的**文字控制属性**（font-、text-、line-height、color）
- 如果子级自己有默认样式或已设置该属性，则继承失效

#### 层叠性

- **相同的属性**会覆盖（后写的生效）
- **不同的属性**会叠加

#### 优先级

选择器范围越大，优先级越低：

```
通配符 < 标签 < 类 < id < 行内样式 < !important
```

**叠加计算规则**（复合选择器）：

```
(行内样式个数, id选择器个数, 类选择器个数, 标签选择器个数)
```

- 从左向右依次比较个数，同一级个数多的优先级高
- 个数相同则向后比较
- `!important` 权重最高，**继承**权重最低

### 2.7 Emmet 写法

| 写法 | 结果 |
| --- | --- |
| `标签名.类名` | 带类的标签，如 `div.box` |
| `标签名#id名` | 带 id 的标签，如 `div#box` |
| `div + p` | 同级（兄弟）标签 |
| `div > p` | 父子级标签 |
| `div*3` | 3 个相同标签 |
| `div{内容}` | 带内容的标签 |

### 2.8 背景属性

```css
background-color: pink;                            /* 背景色 */
background-image: url(./images/bg.png);            /* 背景图 */
```

**背景图平铺** `background-repeat`：

| 值 | 说明 |
| --- | --- |
| `no-repeat` | 不平铺 |
| `repeat` | 平铺（默认） |
| `repeat-x` | 沿水平方向平铺 |
| `repeat-y` | 沿垂直方向平铺 |

**背景图位置** `background-position`：

```css
background-position: center top;   /* 关键字：left/right/center/top/bottom */
background-position: 20px 30px;    /* 坐标：水平 垂直 */
```

- 关键字顺序可颠倒；只写一个关键字，另一个方向默认居中
- 只写一个数字表示水平方向，垂直默认居中

**背景图缩放** `background-size`：

| 值 | 说明 |
| --- | --- |
| `cover` | 等比缩放，**完全覆盖**背景区（图片可能被裁切） |
| `contain` | 等比缩放，**完全装入**背景区（可能留白） |
| 百分比 / 数字+单位 | 按盒子尺寸计算 |

**背景图固定** `background-attachment: fixed`（不随页面滚动）。

**复合属性** `background`：

```css
background: pink url(./bg.png) no-repeat center/cover;
```

> 多个属性值用空格隔开，不区分顺序；`position/size` 之间用 `/` 分隔。

### 2.9 元素显示模式

🆕 标签分三种显示模式，决定了它**占不占一行、能不能设宽高**。

| 显示模式 | 特点 | 代表标签 |
| --- | --- | --- |
| **块级 block** | 独占一行；宽高可设；默认宽度撑满父级 | `div` `p` `h1~h6` `ul` `li` `table` `form` |
| **行内 inline** | 一行可放多个；**宽高设置无效**；宽高由内容撑开 | `span` `a` `strong` `em` `label` |
| **行内块 inline-block** | 一行可放多个；**宽高可设** | `img` `input` `button` `td` |

```css
display: block;         /* 转块级 */
display: inline;        /* 转行内 */
display: inline-block;  /* 转行内块 */
display: none;          /* 隐藏元素（不占位置） */
```

**注意点**：

- 行内块之间在 HTML 里换行写，会产生**几像素的间隙**（把父级 `font-size: 0` 可解决，或实际用 Flex 布局）
- `<img>` 是行内块，所以图片底部会有**几像素空白缝隙**，解决办法：

```css
img { display: block; }      /* 方法一：转块级 */
img { vertical-align: middle; } /* 方法二：改垂直对齐方式 */
```

> `vertical-align` 只对**行内和行内块元素**生效，常用于图片与文字的对齐。

### 2.10 更多选择器

🆕

#### 结构伪类选择器（按位置选元素）

```css
li:first-child { }      /* 第一个 */
li:last-child { }       /* 最后一个 */
li:nth-child(3) { }     /* 第 3 个 */
li:nth-child(2n) { }    /* 偶数个（2、4、6…） */
li:nth-child(2n+1) { }  /* 奇数个 */
li:nth-child(-n+3) { }  /* 前 3 个 */
```

- `n` 从 0 开始递增，`even` = 偶数，`odd` = 奇数
- 常用场景：表格斑马纹 `tr:nth-child(odd) { background: #f5f5f5; }`
- `:nth-child` 要求"是该父元素的第 n 个子元素**且**是指定标签"，容易失效；
  改用 `:nth-of-type(n)`（只数同类型标签）更稳

#### 属性选择器

```css
input[type="text"] { }     /* 选中 type 为 text 的 input */
a[target="_blank"] { }     /* 选中新窗口打开的链接 */
```

#### 焦点伪类

```css
input:focus {
  border-color: #378ADD;
  outline: none;   /* 去掉默认蓝色描边，记得用其他样式替代，别直接删掉 */
}
```

> 做登录框时，"输入框被点中时高亮"就是 `:focus` 实现的。

### 2.11 伪元素

🆕 用 CSS **凭空造出一个元素**，不需要在 HTML 里写标签。

```css
.box::before { content: "★"; }   /* 在元素内容前面插入 */
.box::after  { content: ""; }    /* 在元素内容后面插入 */
```

- **必须写 `content` 属性**，否则不显示
- 默认是行内元素，要设宽高需转 `display: block / inline-block`
- 常见用途：做小图标、做装饰线、**清除浮动**

```css
/* 清除浮动（经典写法，先记住，后面学浮动会用到） */
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

> 写法上 `::before`（双冒号）是 CSS3 规范，`:before`（单冒号）也能用。

### 2.12 常用装饰与溢出属性

| 属性 | 说明 | 示例 |
| --- | --- | --- |
| `border-radius` | 圆角，`50%` 就是正圆 | `border-radius: 8px` |
| `box-shadow` | 盒子阴影 | `box-shadow: 0 2px 8px rgba(0,0,0,.1)` |
| `text-shadow` | 文字阴影 | `text-shadow: 1px 1px 2px #000` |
| `opacity` | 整体透明度 0~1（**连子元素一起透明**） | `opacity: .5` |
| `cursor` | 鼠标样式：`pointer`（小手）/ `default` / `not-allowed` | `cursor: pointer` |
| `overflow` | 内容溢出处理 | 见下 |
| `list-style` | 列表符号，做导航必写 `none` | `list-style: none` |
| `outline` | 轮廓（不占空间，常用于 focus） | `outline: none` |

**overflow 溢出处理**：

| 值 | 效果 |
| --- | --- |
| `visible` | 默认值，溢出部分照常显示 |
| `hidden` | 溢出部分**裁掉**（还能撑开高度，可解决 margin 塌陷） |
| `scroll` | 无论是否溢出都显示滚动条 |
| `auto` | 溢出时才显示滚动条（最常用） |

> `opacity` vs `rgba`：`opacity: .5` 让**整个元素及其内容**都半透明；
> `background: rgba(0,0,0,.5)` 只让**背景**半透明，里面的文字不受影响。做遮罩层时用后者。

---

