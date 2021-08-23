# 标题：在FPGA中实现脉冲神经网络的脉冲序列编码优化
## 来源：第12届国际高级计算智能会议(ICACI)
## 基本信息：尖刺神经网络(SNN)是一种基于尖刺而非连续值进行信息处理的生物似是而非模型，比神经网络具有更好的硬件友好性。为了使snn能够对自然图像信息进行处理，提出了一种在FPGA上加速输入数据峰值编码的方法。
## 关键词：FPGA、神经形态计算、spike神经网络(SNN)、spike trains 编码

## 输入编码方式
经过转换，数字输入数据的神经网络需要编码成spike模式，以符合spike神经元动力学的要求。一种典型的脉冲串称为泊松分布脉冲串

![image](https://user-images.githubusercontent.com/88994795/130408803-42e55077-4cd5-4444-b0e4-9c905d7919e1.png)
<br>其中rand()为均匀分布在(0,1)中的随机数生成器，c为调节神经元放电率的比例因子，x为分布在(0,1)中的输入图像的像素值。

![image](https://user-images.githubusercontent.com/88994795/130408937-d7c53e61-36e0-43e3-9735-d74e18ee686f.png)
<br>其中I为前一个脉冲和当前脉冲之间的间隔时间，U为分布在(0,1)中的随机数，λ为IF神经元的放电速率。

## 软件算法
![image](https://user-images.githubusercontent.com/88994795/130409085-f6763a98-cbfe-4ebb-930d-016403f0ec33.png)
<br>Frate为(0,1)中归一化分布的输入像素。
<br>Nfire表示spike的总数
<br>T是时间窗口的长度
<br>Finterval存储两个连续峰值之间的间隔时间。
<br>Ftime包括每个尖峰的射击时间

## 硬件友好算法
![image](https://user-images.githubusercontent.com/88994795/130409219-402f9e3e-70f2-49c9-a983-2e68272ca937.png)
<br>Frate为(0,1)中归一化分布的输入像素。
<br>Nfire表示spike的总数
<br>T是时间窗口的长度
<br>Finterval存储两个连续峰值之间的间隔时间。
<br>Ftime包括每个尖峰的射击时间

## 总体结构
![image](https://user-images.githubusercontent.com/88994795/130409364-736639d3-6e2d-4764-8580-886a5a0d60ee.png)

该加速器系统具有如图所示的三级控制层次。

系统级控制器协调:
<br>1)管理SD、ETH等外围设备;
<br>2)片外DRAM与其他子模块(SD、ETH)之间通过系统总线通信。

PS配置：A53 CPU。

输入缓冲区和PE阵列单元之间的流量。顶层控制器在PL中实现。

底层控制器坐标:1)PEs的操作;2) PE单元与输出缓冲区之间通过互连总线进行通信。低电平控制器由每个PE中的控制逻辑电路组成。

## PE结构
![image](https://user-images.githubusercontent.com/88994795/130409782-96307ed3-cc2d-4cd3-a065-e62dfba2164f.png)

四个主要单元：

frate Generator：输入像素可以存储在 (BUFF)中，这个生成器函数在算法2的第一行中用乘数表示。

interval generator：间隔生成器，后Frate生成器将尖峰信号传输到间隔生成器。T为时间窗口参数，
保存在配置信息中，如蓝线所示。在没有DSP IP资源的情况下，采用右移运算代替除法，将数据存储在BRAM配置的间隔缓冲器(BUFI)中。

Spike Generate单元：由加法器和寄存器组成，并在每次加操作后确认时间计数器是否大于T。如果接收到是，则包含神经元地址信息的脉冲将从输出块发送到另一侧互连总线。此外，如果BUFF中没有尖峰，则累加器和输出块将保持低功耗，以节省MUX的能量。底层控制器是一个神经元状态机，它可以通过PE中的神经元指令控制数据流。

## 时序图
![image](https://user-images.githubusercontent.com/88994795/130409951-77e3e594-917f-4341-8938-fd254ff784f2.png)

图3给出了时序图。

Clock信号系统时钟。

BUFF信号表示16位的frate, BUFI信号表示16位的finterval。

SPI CNT信号是输出尖刺序列的13位地址，范围从0到7840尖刺。

首先，BUFI和BUFF可以写入和读取前四个时钟周期。其次，神经元选择单元(OPS)可以根据NSM从BUFF和BUFI读取两个数据。然后它将转移一个穗到外部总线为下一个操作期间。这样，就不需要在保存所有输入像素数据后再进行计算。”显然，并行实现编码操作只需消耗49+4个周期和16个pe，每个选项需要两个时钟完成。

