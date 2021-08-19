# SNNpaper
SNN论文汇总
# AI Chip Paper List
## Table of Contents

 - [About This Project](#about-this-project)
 - [The Chronological Listing of Papers](#the-chronological-listing-of-papers)
   -    [ISCA](#isca)
   -    [ASPLOS](#asplos)
   -    [MICRO](#micro)
   -    [HPCA](#hpca)


## About This Project
​	This project aims to help engineers, researchers and students to easily find and learn the good thoughts and designs in AI-related fields, such as AI/ML/DL accelerators, chips, and systems, proposed in the top-tier architecture conferences (ISCA, MICRO, ASPLOS, HPCA). 

​	This project is initiated by the Advanced Computer Architecture Lab (ACA Lab) in Shanghai Jiao Tong University in collaboration with Biren Research.  Articles from additional sources is being added. Please let us know if you have any comments or willing to contribute.



## The Listing of Tags

​	For guidance and searching purposes, Tags and/or notes are assigned to all these papers . We will use the following tags to annotate these papers.

![Tags](https://github.com/BirenResearch/AIChip_Paper_List/raw/master/tag-list.svg?sanitize=true)

​                               

## The Chronological Listing of Papers


​	We list all AI related articles  collected. The links of <u>paper</u>/<u>slides</u>/<u>note</u> are provided under the title of each article If available. Updating is in progress<br> 

## ISCA
### 2020

| Tags                                                         | -    | Title                                                        | Authors                                             | Affiliations                                                 |
| ------------------------------------------------------------ | ---- | ------------------------------------------------------------ | --------------------------------------------------- | ------------------------------------------------------------ |
| Inference; SIMD  |      | High-Performance Deep-Learning Coprocessor Integrated into x86 SoC with Server-Class CPUs <br>[paper](https://www.iscaconf.org/isca2020/papers/466100a015.pdf) [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/High-Performance%20Deep-Learning%20Coprocessor%20Integrated%20into%20x86%20SoC%20with%20Server-Class%20CPUs.md)|Glenn Henry; Parviz Palangpour                              |     Centaur Technology                                    |
| Inference; dataflow |      |Think Fast: A Tensor Streaming Processor (TSP) for Accelerating Deep Learning Workload <br> [paper](https://www.iscaconf.org/isca2020/papers/466100a145.pdf)   [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/Think%20Fast%20A%20Tensor%20Streaming%20Processor%20(TSP)%20for%20Accelerating%20Deep%20Learning%20Workloads.md)|Dennis Abts; Jonathan Ross | Groq Inc.                     |
| Spiking; dataflow; Sparsity |      |SpinalFlow: An Architecture and Dataflow Tailored for Spiking Neural Networks <br> [paper](http://www.cs.utah.edu/~rajeev/pubs/isca20s.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/SpinalFlow%20An%20Architecture%20and%20Dataflow%20Tailored%20for%20Spiking%20Neural%20Networks.md) |Surya Narayanan; Karl Taht                             | University of Utah                                      |
| Inference; benchmarking |      |MLPerf Inference Benchmark  <br> [paper](https://arxiv.org/pdf/1911.02549.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/MLPerf%20Inference%20Benchmark.md)|Vijay Janapa Reddi; Lingjie Xu, etc.   |       |
| GPU; Compression  |      |Buddy Compression: Enabling Larger Memory for Deep Learning and HPC Workloads on GPUs  <br> [paper](https://www.iscaconf.org/isca2020/papers/466100a926.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/Buddy%20Compression%20Enabling%20Larger%20Memory%20for%20Deep%20Learning%20and%20HPC%20Workloads%20on%20GPUs.md) |Esha Choukse; Michael Sullivan                             |    University of Texas at Austin; NVIDIA                                 |
| Inference; runtime |      |A Multi-Neural Network Acceleration Architecture  <br>[paper](https://www.iscaconf.org/isca2020/papers/466100a940.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/A%20Multi-Neural%20Network%20Acceleration%20Architecture.md) |Eunjin Baek; Dongup Kwon; Jangwoo Kim                                   |Seoul National University|
| Inference; Dynamic fixed-point |      |DRQ: Dynamic Region-Based Quantization for Deep Neural Network Acceleration  <br> [paper](https://www.iscaconf.org/isca2020/papers/466100b010.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/DRQ%20Dynamic%20Region-based%20Quantization%20for%20Deep%20Neural%20Network%20Acceleration.md)|  Zhuoran Song; Naifeng Jing; Xiaoyao Liang  |Shanghai Jiao Tong University|
| Training; LSTM; GPU  |      |Echo: Compiler-Based GPU Memory Footprint Reduction for LSTM RNN Training  <br> [paper](https://www.iscaconf.org/isca2020/papers/466100b089.pdf)  [note](https://github.com/BirenResearch/AIChip_Paper_List/blob/master/notes/ISCA/Echo%20Compiler-based%20GPU%20Memory%20Footprint%20Reduction%20for%20LSTM%20RNN%20Training.md)|Bojian Zheng; Nandita Vijaykumar           |University of Toronto|
| Inference  |      |DeepRecSys: A System for Optimizing End-to-End At-Scale Neural Recommendation  <br> [paper](https://arxiv.org/pdf/2001.02772.pdf)  [note](notes/ISCA/DeepRecSys_A%20System%20for%20Optimizing%20End-to-End%20At-Scale%20Neural%20Recommendation%20Inference.md) |Udit Gupta; Samuel Hsia; Vikram Saraph          |Harvard University; Facebook Inc|
