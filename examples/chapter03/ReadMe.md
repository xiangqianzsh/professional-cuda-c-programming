(base) [admin@host-11-168-33-230 chapter03]$ ./simpleDivergence 1024  20480000
./simpleDivergence using Device 0: NVIDIA A30
Data size 20480000 Execution Configure (block 1024 grid 20000)
warmup      <<< 20000 1024 >>> elapsed 0.000176 sec 
mathKernel1 <<< 20000 1024 >>> elapsed 0.000137 sec 
mathKernel2 <<< 20000 1024 >>> elapsed 0.000161 sec 
mathKernel3 <<< 20000 1024 >>> elapsed 0.000137 sec 
mathKernel4 <<< 20000 1024 >>> elapsed 0.000138 sec 


make Makefile



/export/nsight-systems-2023.2.1/bin/nsys profile --force-overwrite=true -o simpleDivergence.qdrep ./simpleDivergence
 
/export/nsight-systems-2023.2.1/bin/nsys profile --force-overwrite=true -o simpleDivergence.qdrep ./simpleDivergence

```bash
make -f Makefile.nest 
./nestedHelloWorld
./nestedHelloWorld 2


(base) [admin@host-11-168-33-230 chapter03]$ ./reduceInteger
./reduceInteger starting reduction at device 0: NVIDIA A30     with array size 16777216  grid 32768 block 512
cpu reduce      elapsed 0.011685 sec cpu_sum: 2139353471
gpu Neighbored  elapsed 0.001086 sec gpu_sum: 2139353471 <<<grid 32768 block 512>>>
gpu Neighbored2 elapsed 0.000686 sec gpu_sum: 2139353471 <<<grid 32768 block 512>>>
gpu Interleaved elapsed 0.000469 sec gpu_sum: 2139353471 <<<grid 32768 block 512>>>
gpu Unrolling2  elapsed 0.000270 sec gpu_sum: 2139353471 <<<grid 16384 block 512>>>
gpu Unrolling4  elapsed 0.000157 sec gpu_sum: 2139353471 <<<grid 8192 block 512>>>
gpu Unrolling8  elapsed 0.000120 sec gpu_sum: 2139353471 <<<grid 4096 block 512>>>
gpu UnrollWarp8 elapsed 0.000129 sec gpu_sum: 2139353471 <<<grid 4096 block 512>>>
gpu Cmptnroll8  elapsed 0.000136 sec gpu_sum: 2139353471 <<<grid 4096 block 512>>>
gpu Cmptnroll   elapsed 0.000132 sec gpu_sum: 2139353471 <<<grid 4096 block 512>>>



(base) [admin@host-11-168-33-230 chapter03]$ ./nestedReduce2
./nestedReduce2 starting reduction at device 0: NVIDIA A30 array 1048576 grid 2048 block 512
cpu reduce              elapsed 0.000709 sec cpu_sum: 1048576
gpu Neighbored          elapsed 0.000131 sec gpu_sum: 1048576 <<<grid 2048 block 512>>>
gpu nested              elapsed 0.029676 sec gpu_sum: 1048576 <<<grid 2048 block 512>>>
gpu nestedNosyn         elapsed 0.016381 sec gpu_sum: 1048576 <<<grid 2048 block 512>>>
gpu nested2             elapsed 0.000874 sec gpu_sum: 1048576 <<<grid 2048 block 512>>>


```

??? 以下需要好好看一下:
nvprof --metrics inst_per_warp ./reduceInteger
nvprof --metrics gld_throughput ./reduceInteger
nvprof --metrics dram_read_throughput ./reduceInteger
nvprof --metrics stall_sync ./reduce
nvprof --metrics gld_efficiency,gst_efficiency ./reduceInteger



