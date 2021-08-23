# 题目：面向脉冲神经网络FPGA优化设计
## 来源：IEEE 神经网络与学习系统
## 基本信息：本文提出了一种提高SNN性能的参数优化方案，并基于欧拉和三阶龙格-库塔 (RK3)两种数值方法提出了一种(FPGA)在线学习神经形态平台，用于数字实现。
## 关键词：欧拉方法、FPGA、神经形态计算、片上学习、参数优化、龙格-库塔(RK)方法、脉冲神经网络(SNN)、无监督可塑性(STDP)学习。
## LIF（Leaky Intergrate and Fired model）模型
![image](https://user-images.githubusercontent.com/88994795/130400289-f33ca03a-bbd4-4ed7-96f3-3b7109e5f8af.png)
![image](https://user-images.githubusercontent.com/88994795/130400302-d18f0f0d-4111-48da-9ebf-20512f1de936.png)
![image](https://user-images.githubusercontent.com/88994795/130400274-2e88b830-d329-4d9a-9996-2fcd993e2fea.png)
![image](https://user-images.githubusercontent.com/88994795/130400316-0df8e249-cbbb-4291-8a43-f0f097df8e4f.png)
横坐标为输入电流，左边纵坐标为电压，右边纵坐标为电压的微分
![image](https://user-images.githubusercontent.com/88994795/130400371-694e5f77-4cf6-49fd-9341-2556ce1e0f4f.png) ![image](https://user-images.githubusercontent.com/88994795/130400383-ff1d6e65-7033-4c66-9a97-31261dd0d2ff.png)
![image](https://user-images.githubusercontent.com/88994795/130400395-469caeb7-1f5b-44af-95fa-ff8533e68b15.png)

![image](https://user-images.githubusercontent.com/88994795/130400452-01ecc1d7-fd97-4e8d-895a-e22ff6fc25f5.png) 
<br>其中Cm为膜电容，vr为静息膜电位，vth为阈值电位，gl为漏电导，is为输入突触电流。

![image](https://user-images.githubusercontent.com/88994795/130400489-c366be84-8e03-457a-90eb-c0a453611741.png) 
<br>其中ge为与兴奋性通道相关的电导，Eexc为通道的反向电位，gi为与抑制性通道相关的电导，Einh为通道的反向电位。

![image](https://user-images.githubusercontent.com/88994795/130400534-0b8cad8c-0e12-47d2-a5d4-7d180fd76858.png) 
<br>式中，g为电导，τg为时间常数，wi j为突触前神经元j到突触后神经元i的突触权值，TJF为突触前神经元j的放电时间。

## Triplet STDP（三组峰时依赖性可塑性学习）
![image](https://user-images.githubusercontent.com/88994795/130401966-3db1ecec-710d-47ab-bfc0-f26fcf4c3142.png) ![image](https://user-images.githubusercontent.com/88994795/130401981-b271ab5d-6b0b-4f1c-be9d-bd5db866eb73.png)
<br>xj：与突触前神经元j跟踪变量
<br>yi：与突触后神经元i跟踪变量
<br>y1：快的变化
<br>y2：慢的变化

## SNN的架构!
![image](https://user-images.githubusercontent.com/88994795/130406314-7797396a-b236-49ae-8b29-32ccf78c1aca.png)
<br>一个SNN的架构。一个输入层由784个神经元组成，从一个输入图像接收像素值，并及时将它们转换为泊松尖峰序列。一个处理层建立在一个赢家通吃(WTA)网络中，包括100个兴奋性(Exc)和100个抑制性(INh)神经元。

## 欧拉方法
![image](https://user-images.githubusercontent.com/88994795/130406413-46890d76-8736-41de-a3d5-5a8541f8535e.png)
## 龙格库塔方法
![image](https://user-images.githubusercontent.com/88994795/130406482-8be10a66-de11-4f04-95db-236e5a2482dd.png)
## 数字系统框图
![image](https://user-images.githubusercontent.com/88994795/130406529-c61a668a-af05-4151-9032-d70a3a5772ad.png)
<br>数字在线学习系统概述。
处理单元负责管理PC和SNN单元之间的通信。SNN单元处理输入图像并发出尖刺。
在WTA网络中，wexc和winh是兴奋层和抑制层之间恒定的突触权值。
![image](https://user-images.githubusercontent.com/88994795/130406589-071811c1-e951-40ca-ab56-7b51bba40011.png)
<br>用不同的数值方法实现LIF神经元模型的数字实现。

<br>(a)基于欧拉方法的LIF神经元模型设计。电流模块产生输入突触电流。尖峰检测模块检查输出尖峰的出现。

<br>(b)基于RK3方法的设计。当前模块通过MUX反复使用，直到三个中间变量被更新。

![image](https://user-images.githubusercontent.com/88994795/130406733-c1e56acb-c3fa-45f3-b300-45c308df4398.png)
<br>数字实施的STDP学习单元为正权重。
更新。Spre和post代表突触前和突触后的脉冲序列，
分别。μ为学习率。wij是体重变化。
















