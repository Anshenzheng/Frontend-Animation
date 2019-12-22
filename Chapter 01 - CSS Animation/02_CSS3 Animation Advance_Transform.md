# CSS3 Animation Advance - Transform

### 写在前面
掌握了@keyframes的基本使用，我们就可以实现一些简单的动画。如果要实现比较复杂的动画，还需要学习动画中transform等属性的使用。

### transform的使用

#### 概要
transform属性应用于网页元素的2D或3D转换，使用该属性可以控制元素的旋转、缩放、移动、倾斜等。

#### 语法
```HTML5
transform: none|transform-functions
```

![](https://raw.githubusercontent.com/Anshenzheng/Frontend-Animation/master/Chapter%2001%20-%20CSS%20Animation/images/transform-syntax.png)

### transform-functions详解
![](https://raw.githubusercontent.com/Anshenzheng/Frontend-Animation/master/Chapter%2001%20-%20CSS%20Animation/images/transform_example_01.gif)
详细代码示例，见[transform-example-01.html](https://github.com/Anshenzheng/Frontend-Animation/blob/master/Chapter%2001%20-%20CSS%20Animation/css-animation-exampe-01.html)

#### transform function列表

![](https://raw.githubusercontent.com/Anshenzheng/Frontend-Animation/master/Chapter%2001%20-%20CSS%20Animation/images/transform.png)

#### transfrom-origin
在介绍transform functions之前，首先要着重讲一下transform-origin这个属性。
通过transform-origin我们可以指定各种transform functions变换的基点，比如用于指定元素基于指定的基点进行旋转，基于指定的进行拉伸，变形等等。
transform-origin在不指定的情况下，默认值为 "transform-origin: 50%，50%", 即指定元素的中心点。

```CSS
.rotate-element{
    transform-origin: 0 100%; /*指定基点为元素的左下角*/
}

.rotate-element2{
    transform-origin: 20px -50px; /** 指定基点的left值为该元素left+20px, top为该元素的top-50px **/
}
```

#### 1. 旋转(rotate)
1.1 2D平面中按指定角度旋转

**语法** 
rotate(angle)

**示例** 
```CSS
.rotate-element{
	transform: rotate(30deg) /**指定该元素旋转30度**/
	transform-origin: 0 0 /**指定旋转基点为元素左上角**/
	}
```

1.2 3D立体空间中按指定角度进行旋转

**语法** 
rotate(x,y,z,angle)
通过x,y,z三个值确定3D空间中的一个点，从原点到该点的连线即为旋转轴。angle用于指定沿旋转轴旋转的角度，angle取正值时，沿轴顺时针旋转，取负值时，沿轴逆时针旋转。

**示例** 
```CSS
.rotate-element{
	transform: rotate3d(0,1,0,180deg) /**指定元素沿y轴旋转180度**/
	}
```

1.3 3D空间中沿X轴旋转

**语法** 
rotateX(angle)

**示例** 
```CSS
.rotate-element{
	transform: rotateX(30deg)/**沿X轴顺时针旋转30度**/
	}
```

1.4 3D空间中沿Y轴旋转

**语法** 
rotateY(angle)

**示例** 
```CSS
.rotate-element{
	transform: rotateY(30deg)/**沿Y轴顺时针旋转30度**/
	}
```

1.5 3D空间中沿Z轴旋转

**语法** 
rotateZ(angle)

**示例** 
```CSS
.rotate-element{
	transform: rotateZ(30deg)/**沿Z轴顺时针旋转30度**/
	}
```

#### 2. 缩放(scale)
2.1 水平方向缩放

**语法** 
scaleX(sx)
指定元素沿水平方向双向拉伸为原来的sx倍。

**示例** 
```CSS
.scale-element{
	transform: scaleX(2) /**沿水平方向扩大为原来的2倍长**/
}
```

2.2 垂直方向缩放

**语法** 
scaleY(sy)
指定元素沿垂直方向双向拉伸为原来的sy倍。

**示例** 
```CSS
.scale-element{
	transform: scaleY(2) /**沿垂直方向拉扩大为原来的2倍长**/
}
```

2.3 水平及垂直方向同时缩放

**语法** 
scale(sx,sy)
指定元素沿水平方向双向拉伸为原来的sx倍,沿垂直方向双向拉伸为原来的sy倍。

**示例** 
```CSS
.scale-element{
	transform: scaleY(2) /**沿垂直方向拉扩大为原来的2倍长**/
}
```

2.4 3D缩放

**语法** 
scale3d(sx,sy,sz)
指定元素沿水平方向双向拉伸为原来的sx倍,沿垂直方向双向拉伸为原来的sy倍,沿视觉方向(Z轴)双向拉伸为原来的sz倍.

**示例** 
```CSS
.scale-element{
	transform: scale3d(2,2,2) /**3D空间内扩大为原来的2倍**/
		transform: scale3d(1,1,0.5) /**3D空间内扩大为原来的2倍**/

}
```

#### 3. 拉伸(skew)
3.1 沿X轴水平方向倾斜转换

**语法** 
skewX(angle)

**示例**
```CSS
.skew-element{
	transform: skewX(45deg);/**沿X轴方向做45度倾斜变换**/
}
```

3.2 沿Y轴垂直方向倾斜转换

**语法** 
skewY(angle)
```CSS
.skew-element{
	transform: skewY(45deg);/**沿Y轴方向做45度倾斜变换**/
}
```

3.3 沿X轴和Y轴做2D倾斜转换

**语法** 
skew(x-angle,y-angle)
```CSS
.skew-element{
	transform: skew(45deg, 45deg);/**同时沿X,Y轴方向做45度倾斜变换**/
}
```

#### 4. 移动(translate)
4.1 沿X轴方向移动元素

**语法** 
translateX(dx)
```CSS
.translate-element{
	transform: translateX(30px);/**沿水平方向移动30px**/
}
```

4.2 沿Y轴方向移动元素

**语法** 
translateY(dy)
```CSS
.translate-element{
	transform: translateY(30px);/**沿垂直方向移动30px**/
}
```

4.3 2D平面内沿X轴和Y轴方向移动元素

**语法** 
translate(dx, dy)
```CSS
.translate-element{
	transform: translate(30px, 30px);/**同时沿X轴和Y轴移动30px**/
}
```
4.4 3D空间内移动元素

**语法** 
translate3d(dx, dy, dz)
```CSS
.translate-element{
	transform: translate(30px, 30px, 30px);/**3D空间内移动元素**/
}
```

#### 5. 矩阵(matrix)
5.1 通过矩阵对元素在2D平面内做转换

**语法** 
matrix(a,b,c,d,e,f)
对指定元素中所有的点(x_0, y_0)按给定矩阵做变换后得到新的点(x, y) - 
x = a*x_0 + c*y_0 +e
y = b*x_0 + d*y_0 + f
![](https://raw.githubusercontent.com/Anshenzheng/Frontend-Animation/master/Chapter%2001%20-%20CSS%20Animation/images/transform_matrix_01.png)

**由此可见：**

* 参数a - 控制着X轴方向的缩放
* 参数c - 控制着X轴随y的值产生的偏移
* 参数e - 控制着X轴的位移
* 参数b - 控制着Y轴随x的值产生的偏移
* 参数d - 控制着Y轴的缩放
* 参数f - 控制着Y轴的位移

因此，通过矩阵的转换，我们可以实现所有以上通过旋转，缩放，拉伸，位移产生的效果。

**等价效果如下：**
matrix(sx, 0, 0, sy, 0, 0) == scale(sx, sy);
matrix(cosθ, sinθ, -sinθ, cosθ, 0, 0) == rotate(θ)
matrix(1, 0, 0, 1, dx, dy) == translate(dx, dy)
matrix(1, tan(θy), tan(θx), 1, 0, 0) == skew(θx, θy)


5.2 通过矩阵对元素在3D空间内做转换
CSS3中的3维矩阵比2维矩阵复杂很多，从2维到三维，参数从 3*3=9 变为 4*4=16

**语法** 
matrix(a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p)

x = a*x0 + e*y0 + i*z0 + m
y = b*x0 + f*y0 + j*z0 + n
z = c*x0 + g*y0 + k*z0 + o

同上，通过矩阵的转换，我们可以实现所有以上通过旋转，缩放，拉伸，位移产生的3D变换效果。

transform相关的知识就先介绍到这里，下面是用rotate和transform-origin实现的一个经典的8大行星环绕太阳的动画：

**效果图：**
![](https://raw.githubusercontent.com/Anshenzheng/Frontend-Animation/master/Chapter%2001%20-%20CSS%20Animation/images/solar-system.png)

**代码：**
见示例[transform-example-02.html](https://github.com/Anshenzheng/Frontend-Animation/blob/master/Chapter%2001%20-%20CSS%20Animation/transform-exampe-02.html)


