# RC电流

使用Multisim仿真RC电路的电流。  

1. 仿真电路：电路图如下，左边为20V直流稳压源，开关S1，20KΩ电阻R1，5uF电容C1。  

    仿真文件在[Multisim](https://github.com/nostalgia-w/always_forget/tree/master/2019/0322/RC_Current/Multisim)文件夹下。  

    multisim仿真电路如下：  
![电路图](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0322/RC_Current/img/Circuit_diagram.png)

2. 仿真过程：  

    打开S1，给电路供电，观察线路上的电流情况。  
    电流显示突变到最高值，然后下降，但电流峰值小于10mA（=20V/2KΩ）。

    * Multisim仿真效果如下：  
![仿真gif](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0322/RC_Current/img/RC_Current.gif)