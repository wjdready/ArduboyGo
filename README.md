## Arduboy V2

这是一个基于开源游戏机Arduboy制作的Arduboy Go第二代，这个项目完全开源包括硬件设计，外壳和代码。

首先看一下制作Arduboy Go V2 需要哪些东西吧。

### PCB 板
可以通过打开项目文件夹下的 `PCB Project/outputfile` 来获得PCB加工的必要文件。当然`PCB Project`文件夹下包含了电路设计和PCB设计的全部内容。这是一个基于Altium Designer 19 设计的电路图。
![SCH](SCH.png)
其PCB 3D模型如下，正面
![PCB_front](PCB_front.png)
背面
![PCB_back](PCB_back.png)
如果你没有安装Altium Designer也没有关系，在`PCB Project/outputfile`里面已经包含和PCB加工的必要文件，只需要将文件夹下的`PCB.zip`提供给厂家打样就可以了。

### 元器件采购
在`PCB Project/outputfile`文件夹下的`BOM.xls` 提供了板子所需要的所有元器件的清单，甚至在后面已经包含了购买链接。
![BOM](BOM.png)

### 3D 打印外壳
3D打印所需要的文件放在 `3D file` 下面，是step格式的文件。外壳预览图如下：

![3D_front](3D_front.jpg)
反面
![3D_back](3D_back.jpg)


### 组装调试篇
当你将PCB和3D外壳拿去工厂制作，元器件也准备齐全，并且焊接完成后第一步要做的就是下载bootloader，下载bootloader需要使用ISP下载器，你可以在网上购买如图所示的下载器，
![ISP](ISP.jpg)

然后使用杜邦线将下载器和板子上的接口一一接好，打开烧录软件`Progisp.exe`，设置芯片为Atmega32U4，加载`bootloader文件夹`下的`Leonardo-prod-firmware.hex`，然后加载flash
![download](download1.PNG)
然后使用如下熔丝位
![download](download.PNG)，然后加载flash

完成后点击自动即可完成。