# Fourier-transform.github.io
Fourier transform

# 前言
傅里叶变换：傅里叶变换，表示能将满足一定条件的某个函数表示成三角函数（正弦和/或余弦函数）或者它们的积分的线性组合，其应用场景存在于我们日常生活的方方面面！

# 什么是变换？    
在了解变换之前，先得知道什么是**空间的基**   
![空间的基](https://pic1.zhimg.com/v2-7acc6c9236d975e90d0b93b55fa33bb0_r.jpg)   
其中的**自然基**我们很熟悉，就是类似于高中所学的**单位向量**！   
那么对于下面这种我们高中常见的**正交分解法**，很容易把A、B、C三点的坐标转化到自然基中   
![坐标变换](D:\360MoveData\Users\honor\Desktop\learn\1.jpg)   
A(2,1)——>2x+y   
B(1,2)——>x+2y   
C(3,3)——>3x+3y   
从坐标到基的变换就是一个很简单的变换。   
如果再复杂一点，就是我们高中学到的**三维空间+向量**的变换   
![坐标变换](https://tse1-mm.cn.bing.net/th/id/OIP-C.LgB2rt1TbeBS8B1Z0hboBAAAAA?rs=1&pid=ImgDetMain)   
此处不再详细描述  

# 傅里叶分类 
**傅里叶变换**又分成了两种：**傅里叶级数**和**连续傅里叶变换**  

## 傅里叶级数
傅里叶级数：任何周期函数都可以用**正弦函数和余弦函数构成的无穷级数**来表示（选择正弦函数与余弦函数作为基函数是因为它们是正交的）  
![傅里叶级数](https://bkimg.cdn.bcebos.com/pic/3812b31bb051f819505a1c70d1b44aed2e73e789?x-bce-process=image/format,f_auto/watermark,image_d2F0ZXIvYmFpa2UyNzI,g_7,xp_5,yp_5,P_20/resize,m_lfit,limit_1,h_1080)  

### 怎么样理解正弦函数和余弦函数两个是正交的
这里插入两个来自于知乎的资料
![坐标变换](D:\360MoveData\Users\honor\Desktop\learn\2.jpg)  

![坐标变换](D:\360MoveData\Users\honor\Desktop\learn\3.jpg)   


### 回归正题
![坐标变换](D:\360MoveData\Users\honor\Desktop\learn\4.jpg)   

上述三个sin(wt)、sin(2wt)、sin(3wt)三个正弦函数可以合成出一个新的函数(第四个图像所示)

### 时域、频域
时域：就是上述函数中t的定义域
频域：顾名思义就是频率的定义域，上述图像中频率有w、2w、3w

### 傅里叶级数的转化
f1=sin(wt)  
f2=sin(2wt)   
f3=sin(3wt)  
对于新和成的**F(f)=f1+f2+f3**可以转化为由**振幅**和**频率**组成的新的函数**G(h,w)**  
f1=sin(wt)+φ1  
f2=sin(2wt)+φ2   
f3=sin(3wt)+φ3  
注：如果对于个别分函数有自己的相位(φ),那么组成的新函数会再多一个维度(**G(h,w,φ)**),也可以理解为**G(h,w)**这个公式的初始相位一致为0   

### 傅里叶级数坐标变换的可视化
![坐标变换](D:\360MoveData\Users\honor\Desktop\learn\4.jpg)   
![坐标变换](D:\360MoveData\Users\honor\Desktop\learn\5.jpg)  

### 傅里叶级数的公式
![傅里叶级数](D:\360MoveData\Users\honor\Desktop\learn\6.jpg)  

这个公式里面涉及了三个正交基**（1，sin(nwt)，cos(nwt)）**，具体怎么证明，可以利用上述关于正交函数证明的定义证明就行  

## 连续傅里叶变换
像**傅里叶级数**所展示的那种情况在现实生活中不常见，生活中基本上都是非周期性的连续变化。  
但是在介绍连续傅里叶变换之前，得先介绍一个内容：**欧拉公式**（本内容在**复变函数**里面讲到过，有兴趣的可以看一下这本书）

### 欧拉公式  

![欧拉公式](D:\360MoveData\Users\honor\Desktop\learn\7.jpg)  

### 复杂的信号(f(t))
![复杂信号](D:\360MoveData\Users\honor\Desktop\learn\8.jpg)   
这个复杂的函数就可以进行傅里叶变换了
这个复杂的函数里面肯定含有无穷多个w，那我们把这些w全部给他摘出来。

### 怎么摘频率


#### 原理
假设f(t)是内部含有大量的w信息，w信息肯定全部存在于**sin或者cos这种嵌套函数**中。   
那我们使用**sin函数**去与f(t)做一下内积。根据**正交基函数**，那么f(t)函数中的**cos部分**全部被内积算成0了，只剩下sin函数的内容。
同理，那我们使用**cos函数**去与f(t)做一下内积。根据**正交基函数**，那么f(t)函数中的**sin部分**全部被内积算成0了，只剩下cos函数的内容。


#### 简单的展示
![摘w展示](D:\360MoveData\Users\honor\Desktop\learn\9.jpg)

### 开始对f(t)进行内积
![f(t)](D:\360MoveData\Users\honor\Desktop\learn\10.jpg)  
![傅里叶变化展示](D:\360MoveData\Users\honor\Desktop\learn\11.jpg)  

### 得到的F(T)则是经过傅里叶变换后得到的新图形
现在进行其可视化处理   
![傅里叶变化可视化](D:\360MoveData\Users\honor\Desktop\learn\12.jpg)   
因此F(T)也可以用F(w、p、q)表示，其中w为频率、p为实部、q为虚部


# 应用背景
目前最火的应用方面就是声音的处理、人像美颜、生物信息处理  

## 声音处理  
我发现知乎有些内容比我讲的还全面，可以参考这部分的链接   
[声音处理链接](https://zhuanlan.zhihu.com/p/157674510)

## 人像美颜  

[人像美颜链接](https://zhuanlan.zhihu.com/p/407017507)

## 生物信息处理

这个是前段时间看了一篇三代测序文章的内容发现的
[工具链接](https://github.com/icanccwhite/Deepbinner)  
[文章链接](https://www.biorxiv.org/content/10.1101/366526v1)
可以对三代测序的信号数据进行傅里叶转化，然后可以利用转换信息利用深度学习进行多分类。
![生物信息处理](D:\360MoveData\Users\honor\Desktop\learn\13.jpg)
