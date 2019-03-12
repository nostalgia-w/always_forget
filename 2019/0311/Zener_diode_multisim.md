# 稳压二极管

使用Multisim仿真稳压二极管，一是了解其工作方式，二是熟悉Multisim上的稳压二极管的参数。  

1. 稳压管一般工作在反向击穿状态下，在一定的电流范围内，端电压几乎不变，表现出稳压特性。  

    * 稳压管特性曲线如下(图片摘自百度百科)：  
![特性曲线](https://gss0.bdstatic.com/-4o3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=8cc5ea4cd72a283457ab3e593adca28f/c8177f3e6709c93d9c53f4a69c3df8dcd100543a.jpg)

2. 仿真电路：电路图如下，左边为可调直流稳压源，范围为0V~40V；稳压管参数如下，反向击穿电压为5V，反向击穿电流为20mA。  

    仿真文件在[Multisim](https://github.com/nostalgia-w/always_forget/tree/master/2019/0311/Multisim)文件夹下。  

    * multisim仿真电路如下：  
![电路图](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0311/img/Circuit_diagram.png)

    * 稳压管参数如下：  
![稳压管参数](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0311/img/Zener_parameters.png)

3. 仿真过程：调节直流稳压源，从0V开始一直增加。  

    当稳压管两端电压低于5V时，稳压管不导通，稳压管线路上的电流远远小于R1线路上的电流，稳压管两端电压为(U1*R1)/(R1+R2)。  

    当稳压管两端电压高于5V时，稳压管导通，稳压管线路上电流增加，稳压管两端电压稳定在5V，随着直流稳压管电压增加，稳压管两端电压不变，保持在5V，但电流一直增加。  

    * Multisim仿真效果如下：  
![仿真gif](https://raw.githubusercontent.com/nostalgia-w/always_forget/master/2019/0311/img/Zener_diode_multisim.gif)