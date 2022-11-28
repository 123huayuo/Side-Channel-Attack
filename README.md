# README.md

## 2022-11-25
GRU模型学习：   
![GRU](https://github.com/123huayuo/Side-Channel-Attack/blob/main/image/01.png)   
双入双出：当前输入xt；当前节点输出yt；上一节点传递的隐状态ht-1；传递给下一节点的隐状态ht   
![GRU](https://github.com/123huayuo/Side-Channel-Attack/blob/main/image/02.png)   
GRU有两个门：重置门r(新输入结合先前记忆)/更新门z(先前记忆起的作用)。  
过程:  
(1)利用重置门对输入ht-1进行重置后，与输入xt拼接，再通过一个tanh激活函数得到h’即记忆了当前时刻的状态；  
(2)使用更新门z对输入ht-1进行选择性“遗忘”，再对h’进行选择性“记忆”，综合后得到输出ht。即忘记传递下来的 ht−1 中的某些维度信息，并加入当前节点输入的某些维度信息。  

## 2022-11-24
阅读文献《RetroIoT: Retrofitting Internet of Things Deployments by Hiding Data in Battery Readings》  
场景：商业物联网设备升级部署缺乏灵活性；  
目标：通过更换可编程电池以编码定制信息，来微创改造部署现有物联网设备；  
创新：1.提出了`一种“可编程”电池取代标准电池的方法RetroIoT`，将自定义命令和数据编码通过电池到IoT设备中；2.设计`两种编码解码技术`，可通过信道发送模拟和数字信息升级设备；  

模拟编码器硬件设计：  
![模拟编码器](https://github.com/123huayuo/Side-Channel-Attack/blob/main/image/03.png)  
输入电压0~3v模拟信号至模拟缓冲器(连接到运放，隔离输入信号与编码器控制电路)；经过调节低压稳压器(LDO)输出3~3.3v模拟信号。  
数字编码器硬件设计：  
![数字编码器](https://github.com/123huayuo/Side-Channel-Attack/blob/main/image/04.png)  
利用I2C控制的DAC转换器电流汇聚/源集成电路，调整并输出128个值的可变输出电流，以产生一个可变的输出电压信号。电压信号经LDO稳压后，使用超低功耗MCU通过现有DAC的I2C接口发送符号。单片机使用电流感应放大器来监测物联网设备的电流输出并计算设备的传输间隔。  
能量收集电源设计：  
![能量收集电源](https://github.com/123huayuo/Side-Channel-Attack/blob/main/image/05.png)  
该能量收集电源连接到现有的电源和接地端，用收割机(超级电容)取代能量存储，之后用电压调节器调节电容器电压，并向系统其余部分提供恒定电压。  
将一个小型微控制器MCU集成到替代电源，观察存储元件的电荷状态和入射的收获能量，并将其传输至云端，由云控制消息调整设备操作以匹配可用的能源限制。  
## 2022-11-23
1.完善侧信道攻击PPT  
2.撰写发明专利  

## 2022-11-20
完成文献整理

## 2022-11-13
完成autojs脚本，控制安卓手机自动开关某一软件  
