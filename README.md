Professional CUDA C Programming
===============================

Included here are the code files for any samples used in the chapters as
illustrative examples.

Each chapter has its own code folder that includes the sample .c and .cu files
for that chapter. The per-chapter folders each also include a Makefile that can
be used to build the samples included.

The common/ directory contains common.h, which includes code that is common to
multiple chapters.



# 我的读书笔记
# chapter1 (还未读)
# chapter2

# chaater3

TODO:
    Fermi/Kepler架构最大计算量这些指标怎么计算
    latency hiding 还需要好好读读
    计算指令吞吐, 延时这些没看太明白, little raw没看太明白
    memory读取带宽, 吞吐这些测算, 需要再看一下, 基于A30跑一把试一下

unrolled loop的好处: 1. 减少条件检查的次数. 2. 更多的独立指令, 可增加指令的并发调度
