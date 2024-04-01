# 今日开源新闻汇总2024-4-1
## 1.
Mozilla Ocho小组在复活节周日发布了Llamafile的新版本。Llamafile是一种分发和运行大型语言模型（LLM）的方法，只需一个文件，使得LLM更容易被开发者和最终用户使用。Llamafile是Mozilla近期推出的较有趣的非浏览器项目之一，目前看来前景光明。
<br>
Llamafile通过利用Llama.cpp，使得处理大型语言模型变得更加方便，易于部署。它可以轻松地将整个LLM打包成一个单文件可执行程序，该程序适用于大多数系统，同时能够利用CPU和GPU执行。
<br>
今天发布的Llamafile 0.7终于支持AVX-512了！在AVX-512启用的CPU上，如AMD Zen 4，测试Llama 0.7的人发现，这种支持使得提示评估时间快了大约10倍。对于那些拥有AVX-512并在CPU上使用Llamafile进行大型语言模型的人来说，这是一个非常好的复活节礼物。
<br>
我已经运行了几个月的Llamafile基准测试，并期待尝试Llamafile 0.7，以查看其在AVX-512 Intel和AMD处理器上的性能提升。
<br>
Llamafile 0.7还带来了BF16 CPU支持、安全修复、各种Windows改进、在Raspberry Pi 5上使用F16权重的提示评估速度现在快了大约8倍，以及其他各种改进。
<br>
更多关于Llamafile 0.7的下载和信息，请通过GitHub获取。
<br>
![图片暂时迷路了！！:(](img/1.png)
<br>
## 2.
开源的Rust编写的Redox OS最近在其内核上取得了“显著”的性能和正确性改进，进一步展示了这个从零开始的操作系统的能力。
<br>
Redox OS已经正确地布线了TLB shootdown支持，改进了信号处理以处理各种bug，需求分页在某些情况下帮助实现了“巨大的性能提升”，新的p2buddy帧分配器已经推出，以及其他各种低级优化，如系统调用优化。
<br>
最新的Redox OS状态更新总结道： 
<br>
*“今年，内核的正确性和原始性能都有了许多改进。信号和TLB shootdown MRs显著提高了内核内存的完整性，并可能消除了许多难以调试和非平凡的heisenbugs。尽管如此，为了提高与移植应用程序的兼容性，仍有很多工作要做，以优化和修复relibc中的bug，最重要的是，更接近一个自托管的Redox。”*
<br>
Redox OS项目一如既往地令人兴奋。
<br>
![图片暂时迷路了！！:(](img/2.png)
<br>
## 3.
GNU Poke 4.0在开发了一年后发布，它增强了这款开源软件，作为一个交互式的二进制数据编辑器，并附带了自己的过程式编程语言。
<br>
GNU Poke 4.0带来了许多用户界面更新，一个新的“pokefmt”工具用于简单的模板系统，各种Poke语言更新，库更新，更新了用于处理不同形式二进制数据的pickles，以及原生Windows构建支持。GNU Poke现在支持在Microsoft Windows系统上构建和运行poke、libpoke和pokefmt。
<br>
关于GNU Poke 4.0发布的更多细节可以通过邮件列表公告获得。
<br>
开发者Jose E. Marchesi在周六还发布了poke-elf 1.0。Poke-ELF 1.0是这个项目的首个版本，是一个功能齐全的GNU Poke pickle，用于编辑ELF对象文件、可执行文件、共享库和核心转储。Poke-ELF 1.0支持多种架构和扩展，并作为GNU Poke项目的一部分正在开发。
<br>
![图片暂时迷路了！！:(](img/3.png)
<br>
## 4.
