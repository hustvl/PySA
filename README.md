<div align="center">

# Pyramid Self-Attention for Semantic Segmentation
</div>

Paper: Pyramid Self-Attention for Semantic Segmentation

By Jiyang Qi<sup>1</sup>, Xinggang Wang<sup>1,2</sup>, Yao Hu<sup>3</sup>, Xu Tang<sup>3</sup>, Wenyu Liu<sup>1</sup>

<sup>1</sup> [School of EIC, HUST](http://eic.hust.edu.cn/English/Home.htm), <sup>2</sup> Hubei Key Laboratory of Smart Internet Technology, <sup>3</sup> [Alibaba Group](https://www.alibaba.com/)

# Introduction

![PySA](resources/PySA.png)

Self-attention is vital in computer vision since it is the building block of Transformer and can model long-range context for visual recognition. However, computing pairwise self-attention between all pixels for dense prediction tasks (e.g., semantic segmentation) costs high computation. In this work, we propose a novel pyramid self-attention (PySA) mechanism which can collect global context information far more efficiently. Concretely, the basic module of PySA first divides the whole image into $R \times R$ regions, and then further divides every region into $G \times G$ grids. One feature is extracted for each grid and then self-attention is applied to the grid features within the same region. PySA keeps increasing $R$ (e.g., from $1$ to $8$) to harvest more local context information and propagate global context to local regions in a parallel/series manner. Since $G$ can be kept as a small value, the computation complexity is low.

# Architecture

<div  align="center">

 <img src="resources/PySA-Series.png" width = "100%" alt="PySA-Series" align=center />

 Overview of the proposed PySA-Series.

 <img src="resources/PySA-Parallel.png" width = "60%" alt="PySA-Parallel" align=center />

Overview of the proposed PySA-Parallel.
</div>

By keeping increasing $R$ (e.g., from $1$ to $8$), models can harvest more local context information and propagate global context to local regions in a parallel/series manner.