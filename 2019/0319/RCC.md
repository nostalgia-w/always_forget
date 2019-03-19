# RCC

RCD钳位电路，可以吸收尖峰。

## 简介

RCC电路常用在50W以下输出功率的开关电源上。特点是结构简单，自激式，不需要振荡电路。  
但RCC电源的频率并不固定，会受输入电压和输出电流的影响。当输入电压最低，同时负载电流最大时，此时工作频率最低。  
当输入电压不断降低，此时RCC电源的工作频率也在不断的降低，变压器开始产生交流声，比如降低至25KHZ以下，人耳能听见。  

## 工作原理  

RCC电路是由Buck-Boost Converter衍生而来。  
![Buck-Boost_Converter]()  

三极管Q1的基极输入为高电平T<sub>on</sub>时，Q1导通，L1上电压为V<sub>L</sub>=V<sub>i</sub>=L*(di/dt)  

L1上电流I<sub>L</sub>=(V<sub>i</sub>*T<sub>on</sub>)/L  

L1此时为储能，D1不导通，Vo的输出由C<sub>o</sub>维持。  

三极管Q1的基极输入为低电平T<sub>on</sub>时，Q1截止，L1储存的能量释放，此时D1导通，L1释放的能量供给C<sub>o</sub>存储能量和负载RL。  

Buck-Boost Converter工作波形图：  
![Buck-Boost_Converter_Waveform]()

若要使V<sub>i</sub>与V<sub>o</sub>之间隔离，可将L1以1:1的方式做成变压器。  
![Buck-Boost_Converter_isolation]()  

将Q1放至N<sub>p</sub>的下面，并将N<sub>s</sub>极性反转，D1与Co跟着极性翻转，此时电路图如下：  
![Buck-Boost_Converter_Adjustment]()  

在此基础上，若将Q1加上驱动绕组及启动电阻，电路就成为简单的RCC电路。  
![RCC]()  

当V<sub>in</sub>提供电压给RCC电路是，经过启动电阻Rs提供电流给Q1的基极，是Q1导通，此时Np线圈有电压，Nb线圈有Np感应出电压，经过电阻Rb给Q1提供较大的电流，使Q1快速进入饱和状态。  

在Q1导通期间，Ns绕组由于极性与Np相反，所以D1不会导通，负载电流由Co提供。

Q1导通时，Ip=Ic呈斜坡状上升，当Ic = β*Ib后，基极的电流已经无法保持Q1饱和导通，Q1脱离饱和区，Q1集电极和发射极之间的电压Vce上升。Vce电压上升使得Np绕组的电压下降，Nb绕组的电压也随之下降，此时Ib电流减少，Q1基极电流不足，Q1关闭。此时，变压器Ns绕组产生反向电动势，Ns绕组使D1导通。  

当变压器储存的能量全部转移到输出端后，

1. Ns绕组上残留的少量能量，使得基极绕组Nb产生电压，Q1再次导通  

2. 启动电阻Rs中部分电流变为开关管基极电流，在正反馈作用下再次导通。



## NOTE！  

1. RCC电路的不稳定性  
RCC电路对元件、布线、生产工艺要求较高，使用劣质元件、水准不高的布板、变压器绕制不恰当，都可能导致RCC电路无法工作，或在正常工作一段时间后失效。

2. 漏感导致的二次击穿  
RCC最常见的也是做典型的失效现象是主开关管烧毁。

## 参考资料

1. [RCC电路架构原理](https://wenku.baidu.com/view/9e618adc195f312b3169a58d.html) Edit by Eric Tseng

2. [分享：从基本到完善的RCC电路原理介绍及问题探讨](http://www.eeworld.com.cn/dygl/2013/1226/article_19703.html)

3. [一种自激式反激变换器的分析和设计](https://github.com/nostalgia-w/always_forget/tree/master/2019/0319/doc) 顾元强，尹斌，吴海新，王先永