# CSS3 Animation

### 写在前面
在前端开发中，许多地方不可避免的需要使用一些动画特效。无须借助Javascript、Flash等技术，单纯通过CSS3便能满足我们的大部分需求。
通过CSS样式，我们可以控制元素的大小，颜色，位置等等，CSS3中的动画基本原理就是使元素的样式在指定时间间隔内变化为另一种样式的效果。
所以CSS3动画中两个基本的要素便是时刻与样式。

创建CSS3动画，我们需要学习@keyframes的使用。

@keyframes即关键帧，我们通过@keyframes在不同的时刻定义网页中元素的CSS的样式，就能创建出当前样式逐渐改变为下一时刻新样式的动画效果。

### @keyframes的使用
@keyframes中我们通过 from/to关键字或者百分比来控制动画的不同时刻，然后指定不同时刻的样式来控制动画。


#### 示例 1
```HTML

@keyframes first-animation
{
    from {background: red;}
    to {background：yellow; }
}

@-moz-keyframes first-animation /* To support the Firefox browser */
{
    from {background: red;}
    to {background：yellow; }
}

@-webkit-keyframes first-animation /*To support Safari & Chrome browser */
    from {background: red;}
    to {background：yellow; }
}

@-o-keyframes first-animation /*To support Opera browser */
    from {background: red;}
    to {background：yellow; }
}
```


#### 示例 2
```HTML

@keyframes first-animation
{
    0% {background: red;}
    100% {background：yellow; }
}

@-moz-keyframes first-animation /* To support the Firefox browser */
{
    0% {background: red;}
    100% {background：yellow; }
}

@-webkit-keyframes first-animation /*To support Safari & Chrome browser */
    0% {background: red;}
    100% {background：yellow; }
}

@-o-keyframes first-animation /*To support Opera browser */
    0% {background: red;}
    100% {background：yellow; }
}
```

示例1和示例2可以实现相同的效果，然而用百分比我们可以通过改变百分比的值更加精细的控制样式的动态变化。

### CSS3 动画
通过@keyframes我们定义了动画，然后需要把它绑定到对应的网页元素上，否则不会产生动画效果。
至少一项两项动画属性绑定到对应的元素上才能产生动画：
 - 动画的名称
 - 动画时长
 
 #### 示例
 把"first-animation"绑定到div元素，时长5秒. 

```HTML5
div{
    animation: first-animation 5s;
    -moz-animation: first-animation 5s;
    -webkit-animation: first-animation 5s;
    -o-animation: first-animation 5s
}
```


详细代码，请参见![css-animation-example-01](css-animation-example-01.html)

### CSS3 动画属性

#### @keyframes
定义动画的具体内容。

#### animation
绑定通过@keyframes创建的动画到指定元素上。

#### animation-name
指定@keyframes动画的名称。

#### animation-duration
指定动画完成一个周期所需要的时间, 默认是0

#### animation-timing-function
指定动画的速度曲线, 默认为 ease。
![](https://raw.githubusercontent.com/Anshenzheng/Frontend-Animation/master/Chapter%2001%20-%20CSS%20Animation/images/animation-timing-function.png)

#### animation-delay
指定动画何时开始，默认为0

#### animation-iteration-count
指定动画的播放次数，默认为1
若需不间断执行，则可指定为infinite

#### animation-direction
指定动画是否在下一周期逆向播放，默认为 normal，即正常播放。
另可取值为alternate，意指动画轮流反向播放。

#### animation-play-state
动画状态 - 是否正在运行或者暂停，默认为running

#### animation-fill-mode
指定元素在动画执行时间之外的状态

使用示例
```HTML5
div{
    animation-name: first-animation;
    animation-duration: 5s;
    animation-timing-function: linear;
    animation-delay: 2s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    animation-play-state: running;
    
    /* Firefox: */
    -moz-animation-name: myfirst;
    -moz-animation-duration: 5s;
    -moz-animation-timing-function: linear;
    -moz-animation-delay: 2s;
    -moz-animation-iteration-count: infinite;
    -moz-animation-direction: alternate;
    -moz-animation-play-state: running;
    
    /* Safari 和 Chrome: */
    -webkit-animation-name: myfirst;
    -webkit-animation-duration: 5s;
    -webkit-animation-timing-function: linear;
    -webkit-animation-delay: 2s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-direction: alternate;
    -webkit-animation-play-state: running;
    
    /* Opera: */
    -o-animation-name: myfirst;
    -o-animation-duration: 5s;
    -o-animation-timing-function: linear;
    -o-animation-delay: 2s;
    -o-animation-iteration-count: infinite;
    -o-animation-direction: alternate;
    -o-animation-play-state: running;
}
```

简写的动画属性
```HTML5
div
{
    animation: myfirst 5s linear 2s infinite alternate;
    
    /* Firefox: */
    -moz-animation: myfirst 5s linear 2s infinite alternate;
    
    /* Safari 和 Chrome: */
    -webkit-animation: myfirst 5s linear 2s infinite alternate;
    
    /* Opera: */
    -o-animation: myfirst 5s linear 2s infinite alternate;
}
```

