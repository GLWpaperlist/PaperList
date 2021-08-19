# SNNpaper
  SNN论文汇总
## 目录

 - [关于项目](#关于项目)
 - [论文列表](#论文列表)
   -    [2021年](#2021年)
   -    [年份二](#年份二)
   -    [年份三](#年份三)
   -    [年份四](#年份四)


## 关于项目
* 这个项目的目的是帮助相关人员更快的了解数字和模拟继集成电路和AI加速器硬件实现相关 的知识。项目整理的论文包括各个顶会(ISCA, MICRO, ASPLOS, HPCA)收录的相关文章，并对其的主要内容和创新点进行了概括，方便快速查找。

* 这个项目由GLW算法组提出并进行相关的维护和更新。如果您有任何好的建议和问题，可以在GitHub上与我们一起讨论。


## 论文列表


## 2021年
### SNN

| 标签                                                         | -    | 题目                                                        | 作者                                             | 单位                                                 |
| ------------------------------------------------------------ | ---- | ------------------------------------------------------------ | --------------------------------------------------- | ------------------------------------------------------------ |
| SNN训练，应用  |      | Spiking Neural Network Based Low-Power Radioisotope Identification using FPGA <br>[论文链接](https://www.iscaconf.org/isca2020/papers/466100a015.pdf)     [简介](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/High-Performance%20Deep-Learning%20Coprocessor%20Integrated%20into%20x86%20SoC%20with%20Server-Class%20CPUs.md)|爱丁堡大学，曼彻斯特大学，利物浦大学，克罗梅克集团                              |     IEEE                                    |
| Inference; dataflow |      |Think Fast: A Tensor Streaming Processor (TSP) for Accelerating Deep Learning Workload <br> [paper](https://www.iscaconf.org/isca2020/papers/466100a145.pdf)   
[note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/Think%20Fast%20A%20Tensor%20Streaming%20Processor%20(TSP)%20for%20Accelerating%20Deep%20Learning%20Workloads.md)|Dennis Abts; Jonathan Ross | Groq Inc.                     |
| Spiking; dataflow; Sparsity |      |SpinalFlow: An Architecture and Dataflow Tailored for Spiking Neural Networks <br> [paper](http://www.cs.utah.edu/~rajeev/pubs/isca20s.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/SpinalFlow%20An%20Architecture%20and%20Dataflow%20Tailored%20for%20Spiking%20Neural%20Networks.md) |Surya Narayanan; Karl Taht                             | University of Utah                                      |
| Inference; benchmarking |      |MLPerf Inference Benchmark  <br> [paper](https://arxiv.org/pdf/1911.02549.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/MLPerf%20Inference%20Benchmark.md)|Vijay Janapa Reddi; Lingjie Xu, etc.   |       |
| GPU; Compression  |      |Buddy Compression: Enabling Larger Memory for Deep Learning and HPC Workloads on GPUs  <br> [paper](https://www.iscaconf.org/isca2020/papers/466100a926.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/Buddy%20Compression%20Enabling%20Larger%20Memory%20for%20Deep%20Learning%20and%20HPC%20Workloads%20on%20GPUs.md) |Esha Choukse; Michael Sullivan                             |    University of Texas at Austin; NVIDIA                                 |
| Inference; runtime |      |A Multi-Neural Network Acceleration Architecture  <br>[paper](https://www.iscaconf.org/isca2020/papers/466100a940.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/A%20Multi-Neural%20Network%20Acceleration%20Architecture.md) |Eunjin Baek; Dongup Kwon; Jangwoo Kim                                   |Seoul National University|
| Inference; Dynamic fixed-point |      |DRQ: Dynamic Region-Based Quantization for Deep Neural Network Acceleration  <br> [paper](https://www.iscaconf.org/isca2020/papers/466100b010.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/DRQ%20Dynamic%20Region-based%20Quantization%20for%20Deep%20Neural%20Network%20Acceleration.md)|  Zhuoran Song; Naifeng Jing; Xiaoyao Liang  |Shanghai Jiao Tong University|
| Training; LSTM; GPU  |      |Echo: Compiler-Based GPU Memory Footprint Reduction for LSTM RNN Training  <br> [paper](https://www.iscaconf.org/isca2020/papers/466100b089.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/Echo%20Compiler-based%20GPU%20Memory%20Footprint%20Reduction%20for%20LSTM%20RNN%20Training.md)|Bojian Zheng; Nandita Vijaykumar           |University of Toronto|
| Inference  |      |DeepRecSys: A System for Optimizing End-to-End At-Scale Neural Recommendation  <br> [paper](https://arxiv.org/pdf/2001.02772.pdf)  [note](notes/ISCA/DeepRecSys_A%20System%20for%20Optimizing%20End-to-End%20At-Scale%20Neural%20Recommendation%20Inference.md) |Udit Gupta; Samuel Hsia; Vikram Saraph          |Harvard University; Facebook Inc|
