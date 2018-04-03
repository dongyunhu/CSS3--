## transform 使用 ##

transform的属性包括：rotate() / skew() / scale() / translate(,) ，分别还有x、y之分，比如：rotateX() 和 rotateY() ，以此类推。

>  transform:rotate()： 含义：旋转；其中“deg”是“度”的意思，如“10deg”表示“10度”下同。
  
    .demo_transform1{-webkit-transform:rotate(10deg);-moz-transform:rotate(10deg)}

>  transform:skew()：  含义：倾斜；
    
      .demo_transform2{-webkit-transform:skew(20deg);-moz-transform:skew(20deg)}

>  transform:scale()：
含义：比例；“1.5”表示以1.5的比例放大，如果要放大2倍，须写成“2.0”，缩小则为负“-”。

    .demo_transform3{-webkit-transform:scale(1.5);-moz-transform:scale(1.5)}

>  transform:translate()：
含义：变动，位移；如下表示向右位移120像素，如果向上位移，把后面的“0”改个值就行，向左向下位移则为负“-”。

    .demo_transform4{-webkit-transform:translate(120px,0);-moz-transform:translate(120px,0)}

>  transform综合：
transform的常用属性就是这些了，下面我们借助transition的帮忙来演示一个关于css3 transform的综合实例：

    .demo_transform5{-webkit-transition:all 1s ease-in-out;-moz-transition:all 1s ease-in-out}
    .demo_transform5:hover{-webkit-transform:rotate(360deg) skew(-20deg) scale(3.0) translate(100px,0);-moz-transform:rotate(360deg) skew(-20deg)scale(3.0) translate(100px,0)}

### animation css3 持续旋转360 ###
      <style>
      .anticon-rotate {
        -webkit-animation: spin 1.5s linear infinite;
        animation: spin 1.5s linear infinite;
      }

      @-webkit-keyframes spin {
        0%   {
            -webkit-transform: rotate(0deg);
            -ms-transform: rotate(0deg);
            transform: rotate(0deg);
        }
        100% {
            -webkit-transform: rotate(360deg);
            -ms-transform: rotate(360deg);
            transform: rotate(360deg);
        }
      }
      @keyframes spin {
        0%   {
            -webkit-transform: rotate(0deg);
            -ms-transform: rotate(0deg);
            transform: rotate(0deg);
        }
        100% {
            -webkit-transform: rotate(360deg);
            -ms-transform: rotate(360deg);
            transform: rotate(360deg);
        }
      }

      </style>
