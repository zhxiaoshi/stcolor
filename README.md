# stcolor: 在Stata绘图中使用中国、日本传统色以及谷歌配色

这个程序包里面包含了552个Stata颜色文件和5个Stata命令。

## 安装
* 首先你需要安装github命令，这个命令是用来安装github上的命令的：

```py
net install github, from("https://haghish.github.io/github/")
```

* 然后就可以安装这个命令了：

```py
github install czxa/stcolor, replace force
```

## 使用
&nbsp;|cncm|jpncm | gcm | rgb2hex | hex2rgb
:---:|:---:|:---:|:---:|:---:|:---:
作用|绘制中国传统色地图|绘制日本传统色地图 | 绘制谷歌配色地图 | RGB颜色转16进制 | 16进制颜色转RGB
基本语法| cncm | jpncm | gcm | rgb2hex 77 25 25, p | hex2rgb #fce8b2, p
&nbsp;|cncm, c(1)|jpncm, c(red) | gcm, c(1)|&nbsp;|&nbsp;
&nbsp;|cncm, c(2)|jpncm, c(brown) | gcm, c(2)|&nbsp;|&nbsp;
&nbsp;|cncm, c(3)|jpncm, c(green) | gcm, c(3)|&nbsp;|&nbsp;
&nbsp;|&nbsp;|jpncm, c(yellow) | gcm, c(4)|&nbsp;|&nbsp;
&nbsp;|&nbsp;|&nbsp; | gcm, c(5)|&nbsp;|&nbsp;

### 前个命令的运行结果

中国传统色|日本传统色
:---:|:---:
![](https://czxb.github.io/mr/20180716a5.png)| ![](https://czxb.github.io/mr/20180716a8.png)
![](https://czxb.github.io/mr/20180716a6.png)| ![](https://czxb.github.io/mr/20180716a9.png)
![](https://czxb.github.io/mr/20180716a7.png)| ![](https://czxb.github.io/mr/20180716a10.png)
![](https://czxb.github.io/mr/20180716a5.png)| ![](https://czxb.github.io/mr/20180716a11.png)

## 谷歌颜色地图
![](https://czxb.github.io/mr/20181018a1.png) | ![](https://czxb.github.io/mr/20181018a2.png)
:---:|:---:
![](https://czxb.github.io/mr/20181018a3.png) | ![](https://czxb.github.io/mr/20181018a4.png)
![](https://czxb.github.io/mr/20181018a5.png) | ![](https://czxb.github.io/mr/20181018a5.png)

## rgb2hex 和 hex2rgb运行结果
rgb2hex 77 25 25, p | hex2rgb #a1a8f2, p
:---:|:---:
![](https://czxb.github.io/mr/20181018b2.png)|![](https://czxb.github.io/mr/20181018b1.png)

### 安装好之后的颜色使用示例
另外的552个颜色文件的作用就是是的上面图片上的颜色可以被直接使用，但是需要注意的是<font color = 'red'>谷歌系列的颜色需要在颜色名称前加个谷歌才能使用。</font>
例如：

```stata
cd "~/Desktop"
cncm //选择一个颜色
sysuse auto, clear
tw sc price headroom, msize(med) mc(章丹) || ///
  lfit price headroom, lw(*1.5) lc(十样锦) ///
  by(for, note("") leg(pos(6) row(1))) sch(plotplain)
```

![](https://czxb.github.io/mr/20180716a12.png)

```r
sysuse auto, clear
tw sc price weight, mc(谷歌pteala700)
```
![](https://czxb.github.io/mr/20181018c1.png)
