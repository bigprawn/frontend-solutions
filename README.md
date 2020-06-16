## 前端开发实际工作中常见的问题及其解决方案
从事互联网行业，大家都知道不要重复造轮子。然而我更想说的是，也请不要重复提问！很多常见的问题被问得太多太多，也被回答得太多次，但是这些问题和答案都是零散地分布在各个角落，而且不一定准确和全面，所以为什么不把它们整理起来呢。按下Ctrl+F就能解决的问题，请不要再浪费时间去提问，也不要浪费别人的时间来回答你的问题。

如果没有找到问题的解决方案，或者对已有方案有任何意见或补充，可以提交 [Issues](https://github.com/bigprawn/frontend-solutions/issues)

### 居中问题
* 通用方案
```
.box {
  display: flex;           // 弹性盒子
  justify-content: center; // 子元素水平居中
  align-items: center;     // 子元素垂直居中
}
```
* absolute/fixed
```
.box {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%); // 向左上方移动自身宽高的一半
}
```
[查看更多](https://segmentfault.com/a/1190000015095402)

### 字体问题
* 通用方案
```
font-family: "Helvetica Neue", Helvetica, Arial, "PingFang SC", "Hiragino Sans GB", "Heiti SC", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
```
* 中文
```
font-family: "PingFang SC", "Hiragino Sans GB", "Heiti SC", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
```
* 英文
```
font-family: "Helvetica Neue", Helvetica, Tahoma, Arial, sans-serif;
```
[查看更多](https://segmentfault.com/a/1190000006110417)

### 响应式方案
* 手机端 设计图-750x1334 (所以尺寸都用vw单位)
* PC端   设计图-1920x1080
```
html,
body {
  min-width: 1100px;
  overflow-x: hidden;
}

html {
  font-size: calc(86px + 14 * (100vw - 1100px) / 820);
}

body {
  font-size: .14rem;
  line-height: 1;
}

@media all and (max-width: 1100px) {
  font-size: 86px;
}

@media all and (max-width: 767px) {
  font-size: 14px;
}
```



