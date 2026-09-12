HTML------
标签:
    成对出现，中间内容
    开始标签，结束标签，结束标签比开始多一个/

骨架：
    html（整个网页）
    head（网页头部）
    title（网页标题）
    body（网页主体）
    ！之后tab快速生成骨架

关系：
    父子
    兄弟

注释：
    添加/删除注释ctrl+/

标题标签：
    h1标签一个网页中只能用一次
    h2~h6没有使用限制

段落标签：
    <p>
        双标签
        每个段落之间有空隙

换行水平线标签（单标签）：
    <br>换行
    <hr>水平线

文本格式化标签：
    strong加粗
    em倾斜
    ins下划线
    del删除线

图像标签：
    可插入图片
    <img src="URL">
        src属性：图片路径
        alt属性：图片描述（图片显示不出来时）
        title属性：图片提示（光标到图片上时）
        ./可直接选择当前目录的照片

路径：
    相对路径：
        当前文件.当前目录、..上一级目录、/进入文件夹
    绝对路径：
        windows从盘符触发
        mac从/触发
        还可以在线网址照片（友情链接）

超链接标签：
    <a href="">文字</a>
        href属性值是跳转地址，是必须属性
            跳转网站直接写网址
            跳转本地文件用相对路径
    target="_blank"
        原来网页一直打开， 跳转时新建窗口
    不知道网站链接时，可以在里面写一个#，就不会进行跳转

音视频标签：
    <audio src="" controls loop></audio>
        controls音频控制面板
        属性名和属性值完全一样，可以简写成一个单词
        loop循环播放
    <video src=""></video>
        muted静音播放
        aotoplay可以在静音下，自动播放

列表，表格，表单

列表：
    无序列表：
        ul嵌套li
        <ul>
            <li></li>
            <li></li>
        </ul>
        ul标签里面只能包裹li标签
        但是，li标签里面可以包裹任何内容
    
    有序列表：
        ol嵌套li
        其他同上
    
    定义列表：
        dl嵌套dt和dd，dl定义列表，dt时标题，dd是详情
        dl只能包含dt和dd
        dt和dd可以包含任何内容

表格：
    table嵌套tr，tr嵌套td/th
        tr是行
            th是表头单元格
            td是内容单元个
        border可以给表格添加边框线
    结构标签：
        thead表格头部
        tbody主要内容
        tfoot汇总信息
    合并单元格：
        跨行合并
            保留上单元格，添加属性rowspan
        跨列合并
            保留左单元格，添加属性colspan
        不能跨结构合并

表单：（登录，注册，手机用户信息）
    input标签:
        <input type="...">
            text=文本框
            password=密码框
            radio=单选框
            checkbox=多选框
            file=上传文件
    标签占位文本： 
        placeholder=""
    单选框：
        给属性添加name属性，实现单选
        默认选中目标可以在后面添加checked
    上传文件：
        multiple:可以多选文件
    多选框：
        默认选中添加checked
    下拉菜单：
    select嵌套option
        select是下拉菜单整体
        option是每一项
        默认选中selected
    文本域：（发布评论，发布微博）
        textarea，双标签
        css设置尺寸
    label标签：
        说明文本
        绑定文字和表单控件，增大点击范围
        <input type="radio" id="man">
        <label for="man">男</label>
        或
        <label><input type="radio">女</label>
    按钮：
        <button type="">anniu</button>
            submit提交按钮，可以提交到后台
            reset重置按钮
            button普通按钮
            省略type属性，功能也是提交

布局标签：
    <div>换行展示
    <span>不换行
    空格实体名称&nbsp；
    <实体名称&lt；  >：&gt；

CSS------
    属性名和属性值成对出现，可以叫做键值对

    引入方式：
        内部：
            写在style里面
        外部：
            开发使用
            放到单独的CSS文件里面
            HTML使用link标签引入
        行内：
            配合JavaScript

    标签选择器：
        使用标签名作为选择器；
        选中同名标签选中同样的样式
    
    类选择器：
        定义类选择器~~.类名
            .red{
                color:red;
            }  
        使用类选择器~~添加class=“类名”
            选择器可以有多个类名
    
    id选择器：
        一般配合js，很少设置css
        定义id选择器~~#id名
        使用id选择器~~标签添加id=”id名“
            同一个id选择器在一个页面之恶能使用一次
    
    通配符选择器:
        *，浏览器自动查找页面所有标签，设置相同的样式
    
    盒子:
        width
        height
        background-color背景色

    字体：
        大小font-size
        粗细font-weight
            数字（400/700）/关键字（normal/bold）
        倾斜font-style
            正常normal 倾斜italic
        行高line-height
            数字+px/数字（当前font-size的倍数）
            垂直居中：行高等于盒子高度属性值（单行文字）
        字体族font-family
            例：font-family：楷体
        复合属性font
            一个属性对应多个值，之间用空格隔开就行（倾斜，加粗，字号/行高，字体，按顺序书写，字体和字号必须书写）
        缩进text-indent
            数字+px
            数字+em（当前标签字号的大小）
        对齐text-align（控制内容）
            left左对（默认）
            center居中
            right右对
        修饰线text-decoration
            none无
            underline下划线
            line-through删除线
            overline上划线
        颜色color
            rgba表示法：rgba（r，g，b，a）a表示透明度
            十六进制表示法#RRGGBB  简写#RGB

    