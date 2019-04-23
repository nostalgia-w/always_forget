# 双向TVS

1. 双向TVS与双向稳压管类似。  
下图是SMCJ18CA的技术手册，其中Breakdown voltage 击穿电压为20V。  
![SMCJ18CA](./img/SMCJ18CA.png)  

2. multisim仿真电路如下，SMJ18CA两端电压是120的交流电，当交流电电压超过20V时，击穿TVS管，TVS管两端电压截止在20V。  
在仿真的时候，示波器上显示的最大电压和最小电压，实际有21.64V。  
![TVS](./img/TVS.gif)  
![xsc1](./img/XSC1.png)
