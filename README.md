# PhysicsEngine
Physics Engine inspired by matter.js

最近发现了Github上的开源物理引擎项目[Matter.js](https://github.com/liabru/matter-js)，对它很感兴趣，发现源码并不算长，算上注释大约1万行左右，值得剖析一番。Matter.js实现一个最小化的2D物理引擎，性能不错，故打算用C#重写并学习之。

由于JS是弱类型，而C#是强类型的，所以不得不还原相应的类型。在重写过程中，我也发现了源码中的一些问题，以及代码冗余，不过都无关紧要。在一万行之内实现一个简单的物理引擎本来就很令人激动了，这样可以以最小的工作量来熟悉物理引擎。

重写过程中，渲染用自带GDI实现，所以只需考虑物理引擎中的代码逻辑即可。因需要最简化代码，故有些内容如Sleep等就略过了，只考虑核心部分，即力的仿真和碰撞检测。

最终，我们的物理引擎有下列几个部分：

- 几何体树
- 物理学意义上的基本对象（如点、点集、边界等）
- 简单的碰撞检测（宽、窄）
- 位置修正
- 速度修正