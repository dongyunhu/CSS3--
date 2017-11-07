___常用全局设置___

    继承 box-sizing
    让 box-sizing 继承自 html ：
    html {
      box-sizing: border-box;
      -moz-box-sizing:border-box; /* Firefox */
      -webkit-box-sizing:border-box; /* Safari */
    }

    给可点击元素添加手型光标
    a[href], input[type='submit'], input[type='image'], label[for], select, button, .pointer {
           cursor: pointer;
    }

    *, *:before, *:after {
      box-sizing: inherit;
    }
    HTML5的离线储存？
       localStorage    长期存储数据，浏览器关闭后数据不丢失；
       sessionStorage  数据在浏览器关闭后自动删除。

    A. 表格自动宽度
       td {
           white-space: nowrap;
         }

___1.animation书写实例___

     .demo1 {
         width: 50px;
         height: 50px;
         margin-left: 100px;
         background: blue;
         -webkit-animation-name:'wobble';/*动画属性名，也就是我们前面keyframes定义的动画名*/
         -webkit-animation-duration: 10s;/*动画持续时间*/
         -webkit-animation-timing-function: ease-in-out; /*动画频率，和transition-timing-function是一样的*/
         -webkit-animation-delay: 2s;/*动画延迟时间*/
         -webkit-animation-iteration-count: 10;/*定义循环资料，infinite为无限次*/
         -webkit-animation-direction: alternate;/*定义动画方式*/
      }

       取值说明：
       --alternate，他的作用是，动画播放在第偶数次向前播放，第奇数次向反方向播放。

       --animation-play-state主要是用来控制元素动画的播放状态。其主要有两个值，running和paused其中running为默认值。
       通过paused将正在播放的动画停下了，
       也可以通过running将暂停的动画重新播放，

    兼容及步骤
      .anim-toRight{
        0%{-webkit-transform:translateX(-32em)}
        100%{-webkit-transform:translateX(0)}
        }
        @-moz-keyframes anim-toRight{
        0%{-moz-transform:translateX(-32em)}
        100%{-moz-transform:translateX(0)}
        }
        @-o-keyframes anim-toRight{
        0%{-o-transform:translateX(-32em)}
        100%{-o-transform:translateX(0)}
        }
        @keyframes anim-toRight{
        0%{transform:translateX(-32em)}
        100%{transform:translateX(0)}
        }
        .anim-toRight{
        /* -webkit-animation:anim-toRight 64s linear; */
        -moz-animation:anim-toRight 64s linear;
        -o-animation:anim-toRight 64s linear;
        animation:anim-toRight 64s linear;
      }


    _1.1实例2--图片鼠标移上左右播放_
      .panoramic {
         width: 150px; 
         height: 150px;
         background: url("http://www.w3cplus.com/sites/default/files/blogs/2015/1507/naxos-greece-big.jpg");
         background-size: auto 100%;
         animation: panoramic 10s linear infinite alternate;
         animation-play-state: paused; /***** paused 指播放动画暂停 ****/
      }
      .panoramic:hover,
      .panoramic:focus {
         animation-play-state: running; /**** running 指播放动画开始 ****/
      }
      @keyframes panoramic {
         to {
           background-position: 100% 0;
         }
      }

___01.实现一个图标元素闪动消失出现动态___

    animation: pulse 2s infinite;
    webkit-animation: pulse 2s infinite;
    -ms-animation: pulse 2s infinite;
    animation: pulse 2s infinite;
    //transform-origin: center center;


___02.input输入框color值可以改变value=“文字”的颜色___

     有背景透明度情况下，placeholder=“文字”，颜色color值不起作用，
     所以如下使用：
     input:-ms-input-placeholder,
     textarea:-ms-input-placeholder {
      color: #f00;
    }
    input::-webkit-input-placeholder,
    textarea::-webkit-input-placeholder {
      color: #fff;
    }/*也可以加input.类名::-webkit-input-placeholder*/


___03.让一个元素居中显示___

    img{
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    /*******IE8不兼容*************************/


___04.background-size: cover; 可以让图片在容器改变大小时仍然保持填充___

    给浮动图片应用shape-outside，让文本围绕一个圆排列,实现文字环绕图片

    img{  
         float: left;
         shape-outside: circle(50%);
       }

___05.给图片设置倒影___
  
    .box-reflect {
      margin: 10px auto;
      width: 200px;
    }
    .box-reflect img {
      -wekbit-box-reflect: left;
      box-reflect: left;
    }
    假设对象生成的倒影在底部，而且需要让生成的倒影离自身有一个20px的间距
    .box-reflect-offset img {
      -webkit-box-reflect: below 20px;
      box-reflect: below 20px;
    }

___06.移动端的平均分配居中显示___

     table
     也许这个技术会被很多人忘记，不过用在移动端确实不错，关键是没有兼容问题的。主要设置父元素的display: table; table-layout:   fixed; width: 100%;，然后   设置子元素为  display: table-cell;即可。

___07.元素全部居中___

     html, body {
       height: 100%;
       margin: 0;
     }

     body {
       -webkit-align-items: center;  
       -ms-flex-align: center;  
       align-items: center;
       display: -webkit-flex;
       display: flex;
     }

___08.文本展示优化___

     有时候字体并不是对于所有设备都显示为最佳效果，所以使用浏览器来帮忙吧：

     html {
        -moz-osx-font-smoothing: grayscale;
        -webkit-font-smoothing: antialiased;
        text-rendering: optimizeLegibility;
     }

___09. 继承 box-sizing___

     让 box-sizing 继承自 html ：

     html {
       box-sizing: border-box;
     }

     *, *:before, *:after {
       box-sizing: inherit;
     }

___10. 像出版物一样，第一个字变得大些___

    p:first-child::first-letter{
       font-family: "papyrus";
       font-size: 28px;
       font-weight: bold;
     }

___11. 创建模糊文本___

    .blurry-text {
       color: transparent;
       text-shadow: 0 0 5px rgba(0,0,0,0.5);
    }

___12. 移除IE中textarea的滚动条___

    textarea { overflow: auto; }


___13. 更改选中文本的样式___

    ::selection{
         color: white;
         background-color: red;
     }

     ::-moz-selection  /* Firefox needs an extra attention for this */
       {
         color: white;
         background-color: red;
       }


___14.接下来重点说一说多行文本溢出显示省略号，如下。___

     display: -webkit-box;
     -webkit-box-orient: vertical;
     -webkit-line-clamp: 3;
     overflow: hidden;

___15.如果想让动画保持突然终止时的状态，就要使用animation-play-state属性___

     div {
         animation: spin 1s linear infinite;
         animation-play-state: paused;
      }

     div:hover {
        animation-play-state: running;
     }

     上面的代码指定，没有鼠标没有悬停时，动画状态是暂停；一旦悬停，动画状态改为继续播放。

___16.<a>链接嵌套___

    *在前端开发当中，超链接<a>标签嵌套<a>标签会出问题：浏览器解析的时候，将它们解析成不嵌套的。
     我们是存在一定的黑魔法的。那就是给<a>标签内部的<a>标签外添加一个<object>标签

    例如：
     <a href="http://www.w3cplus.com">点击我进入w3cplus。点我进入
         <object>
            <a href="http://www.w3cplus.com/book-comment.html">《图解CSS》</a>
         </object>。这里有前端和方面的资讯
     </a>

___17. 伪类___

    :link伪元素代表链接的正常状态，用于选择未访问的链接。在这里需要声明一点，:link伪元素需要在所有此类别的伪元素之前声明。  其顺序为:link,:visited,:hover,:active

    a:link { 
       color: orange;
     }
   如果你的使用方法如下所示，将会被忽略:

     a{
      color: orange;
     }

     :VISITED
     :visited伪类用于已经被访问过的链接。如下所示处于此类伪元素的第二位置(:link伪类之后)。

     a:visited {
         color: blue;
     }

___18. ios fixed 元素可以定位在页面的正确位置。滚动页面时，由于滚动的是 main 内部的 div，因此 footer 没有跟随页面滚动。___
 
     main {
        /* main绝对定位，进行内部滚动 */
        position: absolute;
        top: 50px;
        bottom: 34px;
        /* 使之可以滚动 */
        overflow-y: scroll;
        /* 增加该属性，可以增加弹性 */
        -webkit-overflow-scrolling: touch;
      }


___19.clearfix清除浮动___

    终极版：
     .clearfix:before,.clearfix:after{ 
         content:""; 
         display:table; 
     } 
    .clearfix:after{clear:both;} 
    .clearfix{ *zoom:1;/*IE/7/6*/ }

___20.首字下沉___

    //首行文字为大写
    p::first-line {
      text-transform: uppercase;
    }
    //首个文字为下沉
    p::first-letter {
      font-size: 3em;
      border: 1px solid black;
      background: red;
      float: left;
      padding: 2px;
      margin-right: 4px;
    }
    
    
___app___

    //竖屏时使用的样式
    <style media="all and (orientation:portrait)" type="text/css">
    #landscape { display: none; }
    </style>
    //横屏时使用的样式
    <style media="all and (orientation:landscape)" type="text/css">
    #portrait { display: none; }
    </style> 
