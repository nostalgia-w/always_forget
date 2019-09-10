# 电感和电流波形

使用Multisim仿真电感，同时使用示波器查看电流波形。

1. 仿真电路：电路图如下，左边为直流稳压源，其中xcp1为Current clamp。current clamp在仪器仪表栏的最后一个，把它接入想要检测电流的线路中，然后再接上示波器，即可查看到电流变化波形，双击current clamp可以设置参数。  

    仿真文件在[Multisim](https://github.com/nostalgia-w/always_forget/tree/master/2019/0313/Multisim)文件夹下。  

    * multisim仿真电路如下：  
![电路图](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0313/img/Circuit_diagram.png)

2. 仿真过程：打开和关闭switch，观察流经电感的电流和电感两端的电压。  

    从曲线可以看出，电感两端电压在接通电源后，会突变到电源电压大小12V，然后逐渐下降为0V。但电流没有突变到12mA，而是缓慢上升，直到达到稳态值（I = 12V/1K = 12mA）。

    * Multisim仿真效果如下：  
![仿真gif](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0313/img/Inductance_and_Current_waveform.gif)

## 参考资料

1. [MULTISIM10.0的电流波形查看](http://bbs.elecfans.com/forum.php?mod=viewthread&ordertype=1&tid=283217)  

2. [电感的特性有哪些](http://m.elecfans.com/article/815378.html)

## Note

1. current clamp的图标中间有个绿色的箭头，表示显示的电流方向，所以如果绿色剪头和实际的电流方向相反，会显示负电流。
