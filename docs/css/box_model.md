# 说说你对盒子模型的理解

核心点：盒模型是什么？标准盒子？怪异盒子？
浏览器渲染引擎在渲染html文件时，会根据协议规范将html中的元素渲染成一个个矩形的小盒子，这些一个个的小盒子就是盒模型。

盒模型包括四个部分：content(内容区)，padding（内边距），margin（外边距），border（边框）

盒模型有两种类型，一种是w3c标准盒子，另一种是IE 怪异盒子。

w3c标准盒子就是height设置的是content的高度，width设置的是content的宽度。

IE 怪异盒子就是height设置的包含content+padding+border的高度，width设置的包含content+padding+border的宽度。

通过box-sizing这个css属性可以设置盒模型是标准盒子还是怪异盒子。

box-sizing：content-box就是标准盒子。
box-sizing：border-box就是怪异盒子。

可以这样子记忆，height为content的高度就是正常的，正常的就是标准盒子。怪异盒子是本来不应该存在的异常的盒子。