css3中transition属性的详细介绍

transtion: all (property)  0.5s(duration)  ease-in-out(type)  1s(delay);
               
>  过度函数：
    ease(逐渐慢下来)，
    linear(匀速
    ease-in(由慢到快)，
    ease-out(由快到慢)，
    ease-in-out(先慢到快再到慢)，
    cubic-bezier(该值允许你去自定义一个时间曲线)。

    transition-property: 过渡属性(默认值为all)
    transition-duration: 过渡持续时间(默认值为0s)
    transiton-timing-function: 过渡函数(默认值为ease函数)
    transition-delay: 过渡延迟时间(默认值为0s)

>  写法

     //Mozilla内核
     -moz-transition ： [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'> [, [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'>]]* 
     //Webkit内核
     -webkit-transition ： [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'> [, [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'>]]* 
     //Opera
     -o-transition ： [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'> [, [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'>]]* 
     //W3C 标准
     transition ： [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'> [, [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'>]]* 

