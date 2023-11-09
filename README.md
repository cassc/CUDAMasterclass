Use `nvcc` to compile and run the programs, for example

```bash
nvcc  common.cpp 12_reduction_complete_unrolling.cu  && ./a.out
```

## Some special cases

* Require the `-rdc true` option for dynamic parallelism

``` bash
nvcc -rdc true   common.cpp 14_dynamic_parallelism.cu && ./a.out
```

* `cudaDeviceSynchronize` is deprecated in CUDA 11.0, so we need to add `-D
CUDA_FORCE_CDP1_IF_SUPPORTED` to compile:

``` bash
nvcc -rdc true -D CUDA_FORCE_CDP1_IF_SUPPORTED  common.cpp 14_reduction\ with\ dynamic\ parallelism.cu && ./a.out
```
