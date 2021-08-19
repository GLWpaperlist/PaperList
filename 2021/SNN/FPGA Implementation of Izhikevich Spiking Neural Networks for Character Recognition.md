  
# 题目：FPGA实现Izhikevich脉冲神经网络字符识别模型

## 单位：Clemson University，University of Dayton

## 目标：探索使用FPGA实现大型Izhikevich仿真模型的可行性。（Izhikevich伊日凯维奇）

引言指出，在方法研究和硬件实现上最流行的方法是 integrate-and-fire算法，但这种方法的生物准确性不太好，不能重现很多神经元的脉冲行为，因此lzhikevich（伊日凯维奇）提出了一种新的模型，同时
具有Hodgkin-Huxley神经元模型的高生物精度和integrate-and-fire模型的低计算消耗的优点。
<br>lzhikevich模型和integrate-and-fire模型模仿每个神经元需要13FLOPs（floating point operations)，而Hodgkin-Huxley神经元模型则需要256FLOPs，因此lzhikevich模型在大型建模中非常具有吸引力。
<br>目前，已经有实验来使用FPGA实现这些神经元模型，来研究硬件能否重现神经元的大部分反应，来探究FPGA实现的可行性。
<br>这篇论文主要目的是探索使用FPGA实现大型Izhikevich仿真模型的可行性，使用的方法是之前的论文提出来的在FPGA上实现的基于Izhikevich模型的字符识别脉冲神经网络。

## 工作的主要贡献是：
<br>1）为了在FPGA上实现Izhikevich模型，设计了模块化的处理原件。许多处理元件被配置在片上，每个处理原件都可以用流水线方式处理大量的神经元。每个神经元状态都被存储在片上存储器中。
<br>2）使用处理元件来评估基于FPGA实现的伊日凯维奇模型的特定应用。结果表明FPGA可以提供基于2.2 GHz AMD Opteron 核的软件实现大约8.5倍的提速。

## 结论
在本文中，我们根据伊日凯维奇在两种 FPGA 上的脉冲神经元模型实施了字符识别算法。我们开发了一个模块化的PE，以流水线方式评估大量的伊日凯维奇尖刺神经元。这种基于 PE 的设计
很容易扩展到更大的 FPGA。实现了两个网络尺寸，并显示在等效软件实现（Virtex II Pro 上的 24 ×24 像素图像网络的大约 3.3 倍，Virtex 4 上的 96 ×96 像素图像网络在 2.2 GHz AMD Opteron
内核上的大约 8.5 倍）。
<br>结果表明，FPGA适用于基于皮质的大规模模型模拟。
