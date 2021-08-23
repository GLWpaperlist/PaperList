# 标题：Programmable Architectures for Large-scale Implementations of Spiking Neural NetworksA
## 来源：ISSC 2008
## 基本信息：本文重点讨论了目前在可重构fpga上实现大规模snn所面临的挑战。本文提出了一种新型的、大规模的现场可编程神经网络(FPNN)架构，该架构包含低功耗的模拟突触和SNN神经元，并使用片上网络(Network on Chip)架构进行互连，用于SNN尖包路由和SNN配置。给出了FPNN体系结构可扩展性的初步结果。
## 关键词：NoC（片上网络）, SNN（脉冲神经网络）, FPNN（现场可编程神经网络）
## 总体结构
![image](https://user-images.githubusercontent.com/88994795/130414576-6cda1058-4fbb-421b-8eca-5ad779760fb5.png)

FPNN总体结构

由I/O块包围的tiles。神经块在北、东、南、西方向连接，形成最近邻连接方案。每个神经块都可以通过编程实现神经元级的功能。通过编程实现了FPNN的功能和连通性，在FPNN体系结构上实现了SNN。

## 神经单元块
![image](https://user-images.githubusercontent.com/88994795/130414662-b9e7bf50-bf53-49dc-98e6-0ab90b92e8b4.png)

<br>Spike I/P：在单个突触细胞上引发一个尖峰
<br>Spike O/P：从神经元接收尖峰事件。
<br>Mode：指定平铺操作;即运行时或配置编程
<br>Indexing bus：用于定位单个突触细胞(通过地址解码器)，以接收脉冲事件或配置数据。
<br>ACK：确认正确的突触定位
<br>The Config Data bus：用于向单元发送配置数据。电池配置连接到q全球电压线，V，这是每个瓷砖共同的，并运行在整个设备。

## 细胞突触单元
![image](https://user-images.githubusercontent.com/88994795/130414816-8eea0ca2-e82e-4ac4-9be9-6e13f41bb5b4.png)

![image](https://user-images.githubusercontent.com/88994795/130414828-d86dba48-057f-4163-b99b-f09444f96d32.png)

一种新的权值分布和存储架构如图4所示，它允许任意数量或组合的p突触在FPNN配置过程中被硬连线到可编程权值电压水平。V1-Vq轨提供一系列电源重量(电压)，选择使用数字控制模拟开关(S1-Sp)。通过突触电流的积累，每个突触细胞内单独可编程的权重结合在一起。
表1举例说明了突触细胞重量


