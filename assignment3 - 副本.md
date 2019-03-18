###第三次作业

- 姓名：王宇桁
- 班级：自动化61
- 学号：2160504021
- 提交时间：19/3/15


**摘要：**直方图均衡化是图像处理领域中利用图像直方图对对比度进行调整的方法。通过这种方法，亮度可以更好地在直方图上分布。这样就可以用于增强局部的对比度而不影响整体的对比度，直方图均衡化通过有效地扩展常用的亮度来实现这种功能。本次作业中，我主要通过C++以及OPENCV实现直方图的相关操作。


-----------
##（1）将图像的直方图画出

为了将直方图画出，统计灰度图当中0-255不同灰度值的元素个数进行统计,并通过opencv的line函数划线表示出来。我主要使用了calcHist函数得到了图片的直方图信息，并使用normalize对直方图信息进行了归一化处理，从而可以将每个图片的直方图显示出来。

**运行结果**

*citywall*
![citywall](https://i.imgur.com/6RUaao5.png)
*citywall1*
![citywall1](https://i.imgur.com/kzux9xN.png)
*citywall2*
![citywall2](https://i.imgur.com/OiBO13h.png)
*elain*
![elain](https://i.imgur.com/ppuPqr5.png)
*elain1*
![elain1](https://i.imgur.com/Ln7VMu8.png)
*elain2*
![elain2](https://i.imgur.com/dW85BHM.png)
*elain3*
![elain3](https://i.imgur.com/O2T5Z1r.png)
*lena*
![lena](https://i.imgur.com/vd1v8mg.png)
*lena1*
![lena1](https://i.imgur.com/xXCbm3h.png)
*lena2*
![lena2](https://i.imgur.com/Olov8xv.png)
*lena3*
![lena3](https://i.imgur.com/kgharVK.png)
*woman*
![woman](https://i.imgur.com/kCeWtRz.png)
*woman1*
![woman1](https://i.imgur.com/Uzl5OYE.png)
*woman2*
![woman2](https://i.imgur.com/RBsUYHK.png)


**结果分析**
从直方图的输出结果可以看到
1. 四张原图的直方图分布比较均匀，故图像显示正常。
2. 较暗的图片相对应的直方图分布在低亮度区域较为集中。
3. 相反，较亮的图片直方图在高亮度区域分布较为集中。
----------
##（2）将图片进行直方图均衡
>直方图均衡化是图像处理领域中利用图像直方图对对比度进行调整的方法。 通过这种方法，亮度可以更好地在直方图上分布。 这样就可以用于增强局部的对比度而不影响整体的对比度，直方图均衡化通过有效地扩展常用的亮度来实现这种功能。

在计算出原始图像的直方图之后，根据概率的方法，将原直方图各个部分的值映射到新的直方图上，新的直方图分布较为均匀，从而实现直方图均衡。

**运行结果**

*citywall*
![citywall](https://i.imgur.com/G5Ya3d5.png)
![citywall1](https://i.imgur.com/IAywbGK.png)
![citywall2](https://i.imgur.com/Gv3L50j.png)

*elain*
![elain](https://i.imgur.com/AYMq6DJ.png)
![elain1](https://i.imgur.com/xWp3HMT.png)
![elain2](https://i.imgur.com/NIH4Ptd.png)
![elain3](https://i.imgur.com/9zZXqAm.png)

*lena*
![lena](https://i.imgur.com/pL7k8Ob.png)
![lena1](https://i.imgur.com/EnzczPo.png)
![lena2](https://i.imgur.com/v7U98hS.png)
![lena3](https://i.imgur.com/iCpR9VT.png)

*woman*
![woman](https://i.imgur.com/U1t47WC.png)
![woman1](https://i.imgur.com/TLnkx2m.png)
![woman2](https://i.imgur.com/SolHcYT.png)

**结果分析**
从直方图均衡的结果可以看到
1. 四张原图由于原本的直方图分布比较均匀，故直方图均衡的效果并不明显。
2. 其余几张原本经过处理，直方图分布严重不均的则直方图均衡效果较为明显。
----------
##（3）直方图匹配
>直方图匹配又称为直方图规定化，是指将一幅图像的直方图变成规定形状的直方图而进行的图像增强方法。即将某幅影像或某一区域的直方图匹配到另一幅影像上,使两幅影像的色调保持一致。
在作业中选择四张原始未经处理的图像的直方图作为模板直方图，将其余的几张图片进行直方图匹配。

**运行结果**

*citywall*
![citywall1](https://i.imgur.com/PTq8NY8.png)
![citywall2](https://i.imgur.com/PDy8PPg.png)

*elain*
![elain1](https://i.imgur.com/ZqQU0Ut.png)
![elain2](https://i.imgur.com/hyOzwMU.png)
![elain3](https://i.imgur.com/dK9Kbne.png)

*lena*
![lena1](https://i.imgur.com/MyGQHHY.png)
![lena2](https://i.imgur.com/xErJnBi.png)
![lena3](https://i.imgur.com/gW54tGm.png)

*woman*
![woman1](https://i.imgur.com/yxtoavb.jpg)
![woman2](https://i.imgur.com/PS2G4vw.jpg)

**结果分析**
由直方图匹配的结果可见，经过处理后的几张图片的直方图都倾向于四张原始图片的直方图进行了新的映射，从而实现了图像质量的增强，这种图像增强方式相较于直方图均衡要显得更加灵活。
----------
##（4）局部直方图增强
>直方图匹配和直方图均匀化的直方图处理方法是全局性的，在某种意义上，像素是被基于整幅图像灰度满意度的变换函数所修改的，这种全局方法适用整个图像的增强，但有时对图像小区域细节的局部增强也仍然是适用的。

在作业中，首先计算出原始图像的标准差以及方差。之后以图上每个元素为中心取7*7的邻域，计算每个邻域的标准差以及均值，将其与原始图片的均值与标准差进行比较，判断其是否需要增强。

**运行结果**
![elain](https://i.imgur.com/PP6G2OE.png)
![lena](https://i.imgur.com/ruQ5ncK.png)

**结果分析**
由上面的结果可以看出，不同于直方图匹配或均衡的整体增强的效果，局部直方图增强能够有选择地增强图片中相较于其他部分较暗的部分，而不会影响到其他地方。

##（5）直方图分割
>图像分割就是把图像分成若干个特定的、具有独特性质的区域并提出感兴趣目标的技术和过程。它是由图像处理到图像分析的关键步骤。现有的图像分割方法主要分以下几类：基于阈值的分割方法、基于区域的分割方法、基于边缘的分割方法以及基于特定理论的分割方法等。

在作业中，主要采用了阈值分割的方法。首先选定初始阈值，计算高于阈值以上部分的均值与阈值一下的均值，将两个均值再取平均作为新的阈值。不断重复过程，知道阈值变化小于设定的要求即可停止。最后根据确定的阈值，进行图像分割。

**运行结果**
![elain](https://i.imgur.com/b6O1VuN.png)
![woman](https://i.imgur.com/xe3JO7h.png)

**结果分析**
由处理结果可见，成功将图像进行了分割。

----------------
##参考文献

数字图像处理 冈萨雷斯