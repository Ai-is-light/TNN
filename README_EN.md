[中文版本](README.md)
#  <img src="./TNN.png" width = "50%" height = "50%"/>


## Introduction

TNN is a high-performance and lightweight inference framework for mobile devices. It provides lots of advanced features such as cross-platform, model-compression, and code-pruning. TNN, inspired by mainstream open-source industry frameworks, integrates and leverages Youtu Lab's Rapidnet, ncnn framework. It also combines the efforts of the deep-learning framework Oteam from all departments(PCG, TEG, IEG) to create an enterprise-level mobile inference engine.
TNN is currently deployed to support various products in Youtu Lab and Guangying Studio.

## Features

#### Outstanding Performance
* Computation optimization
    * The backend operators are primely optimized to make the best use of computing power in different architectures, regarding instruction issue, throughput, delay, cache bandwidth, cache delay, registers, etc..
    * The TNN performance on mainstream hardware platforms (CPU: ARMv7, ARMv8, GPU: Mali, Adreno, Apple) has been greatly tuned and improved.
    * The convolution function is implemented by various algorithms such as Winograd, Tile-GEMM, Direct Conv, etc., to ensure efficiency under different parameters and sizes.
    * Op fusion: TNN can do an offline analysis of network graph, fuse multiple simple operations and reduce overhead such as redundant memory access and kernel startup cost.

* Low precision computation acceleration
    * TNN supports INT8/FP16 mode, reduces model size & memory consumption, and utilizes specific hardware low-precision instructions to accelerate calculations.
    * TNN supports INT8 WINOGRAD algorithm, (input 6bit), further reduces the model calculation complexity without sacrificing the accuracy.
    * TNN supports mixed-precision data in one model, speeding up the model's calculation speed while preserving its accuracy.

* Memory optimization
    * Efficient "memory pool" implementation: Based on a full network DAG analysis, the implementation reuses memory between non-dependent nodes which reduces memory cost by 90%.
    * Cross-model memory reduces: This supports external real-time design for network memory so that multiple models can share mutual memory.

* Performance comparison among mainstream models: TNN outperforms other mainstream open-source mobile high-performance frameworks.

    * Kirin970：

    <img src="doc/cn/imgs/970.jpg" width="512" alt=华为麒麟970平台 />

    * Snapdragon 835：

    <img src="doc/cn/imgs/835.jpg" width="512" alt=高通骁龙835平台 />

### Universal & Lightweight：

#### TNN architecture diagram：

   <img src="doc/cn/imgs/tnn_architect.jpg" width="512" alt=TNN架构 />

* TNN supports TensorFlow, Pytorch, MxNet, Caffe, and other training frameworks through ONNX, leveraging the continuous improvement of the ONNX open-source society.
  Currently TNN supports 55 ONNX operators, and will be developed to cover 80 operators shortly, consisting of most of the mainstream CNN operators needed.
* TNN runs on mainstream operating systems (Android, iOS, embedded Linux, Windows), and is compatible with ARM CPU, GPU hardware platform (Da Vinci NPU will be supported soon)
* TNN is constructed through Modular Design, which abstracts and isolates components such as model analysis, graph construction, graph optimization, low-level hardware adaptation, and high-performance kernel.
   It uses "Factory Mode" to register and build devices, that tries to minimize the cost of supporting more hardware and acceleration solutions.
* TNN's running time does not rely on any third-party libraries. The size of the CPU dynamic library is only around 400KB, and it provides basic image conversion operations, which are light-weight and convenient. TNN uses unified models and interfaces across platforms and can switch easily by configuring just one single parameter.

## Install
* [Compile and Install](doc/en/user/compile_en.md) 

## Usage
* [Model Support](doc/en/user/support_en.md)
* [Model Convertion](doc/en/user/convert_en.md)
* [Demo](doc/en/user/demo_en.md)
* [API Usage](doc/en/user/api_en.md)
* [Test](doc/en/user/test_en.md)
* [Performance Profiling](doc/en/development/profiling_en.md)
* [Model Quantization](doc/en/user/quantization_en.md)

## Integration & Development
* [Model Check](doc/en/development/model_check_en.md)
* [Code Architectures](doc/en/development/architecture_en.md)
* [Unit Test](doc/en/development/unit_test_en.md)
* [Contributing](doc/en/development/contributing_en.md)

## FAQ

* [FAQ](doc/en/faq_en.md)


## License

* [Apache License 2.0](LICENSE)

## Acknowledgement
TNN referenced the following projects：

* [ncnn](https://github.com/Tencent/ncnn) 

* [MNN](https://github.com/alibaba/MNN)

## Join Us

* Scan the QR code to join the TNN discussion group：
    <img src="doc/cn/imgs/group.jpg" height="256"/>

* Welcome to join [Yunfan (Deep Learning Framework and Acceleration) Oteam] (http://mk.oa.com/coterie/175/home) deep-learning framework and acceleration technology, to create first-class industry influence, empower products, and make real values for business and customers.
* Welcome to join the TNN mobile inference framework development team, to create an enterprise-level unified mobile inference framework.

