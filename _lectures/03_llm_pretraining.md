---
type: lecture
date: 2024-12-16T8:00:00+4:30
title: LLM Pre-training and Beyong
tldr: "Short text to discribe what this lecture is about."
thumbnail: /static_files/presentations/lec.jpg

# 添加slides附件
links: 
     - url: /static_files/slides/3.1-GPT-1,GPT-2.2025.01.16.pdf
       name: "第一节slides"

     - url: https://www.bilibili.com/video/BV1CPk5YRE35/?spm_id_from=333.1387.list.card_archive.click&vd_source=f390fbd44eabbd79d483210d5a4d770e
       name: "第一节视频(bilibili)"

     - url: /static_files/slides/3.2-Scaling-Laws-2025.02.02.pdf
       name: "第二节slides"

     - url: https://www.bilibili.com/video/BV1LACYYAEPM/?spm_id_from=333.1387.list.card_archive.click&vd_source=f390fbd44eabbd79d483210d5a4d770e
       name: "第二节视频(bilibili)"
    
     - url: /static_files/slides/3.3-Distributed-Training-2025.02.02.pdf
       name: "第三节slides"

     - url: https://www.bilibili.com/video/BV1gfwreaEhH?spm_id_from=333.788.videopod.sections&vd_source=f390fbd44eabbd79d483210d5a4d770e
       name: "第三节视频(bilibili)"

       
     
# links: 
#     - url: /static_files/presentations/lec.zip
#       name: notes
#     - url: /static_files/presentations/code.zip
#       name: codes
#     - url: https://google.com
#       name: slides
---
- GPT-1 && GPT-2
    - NLP中的预训练-微调范式: CoVe、ELMo、ULMFiT、GPT-1、BERT、GPT-2
    - GPT-1 && GPT-2: Pre-traring LM + Large scale  ==> zero-shot 
    - 编程实践：[阅读GPT-1/GPT-2代码；训练124M GPT-2](https://github.com/10Kpapers/llm101_codes/tree/main/%E7%AC%AC%E4%B8%89%E7%AB%A0LLMPre-trainingandBeyond/3.1GPT-1-and-GPT-2)
- Train-time Compute Scaling Laws
    - 解析(Train-time Compute) Scaling Laws for LM, Empirically 
    - 计算 GPT模型参数和FLOPs
    - Kaplan Scaling Laws && Chinchilla Scaling Laws
    - 编程实践：[Scaling Laws for MNIST](https://colab.research.google.com/drive/1uOUO-zqEpTmPJkeVfzZZzi8zCo94nGAM#scrollTo=YKILkuscd3Zu)
- LLM预训练之分布式训练：数据并行、模型并行、混合精度训练、分布式通信
  - 数据并行(Data Parallelism)
    - DDP(PyTorch), Sharded Data Parallelism: DeepSpeed-ZeRO
    - 分布式通信 (Distributed Communication)
    - 混合精度训练(Mixed Precision Training)和常见数据格式
  - 模型并行(Model Parallelism)
    - 张量并行(Tensor Parallelism, TP)
    - 流水线并行(Pipeline Parallelism, PP)
    - 序列并行(Sequence Parallelism, SP)
    - 上下文并行(Context Parallelism, CP) 
    - 专家并行(Expert Parallelism, EP)
    - 分布式代码之[picotron](https://github.com/huggingface/picotron)

- GPT-3 and Beyond
    - 涌现、幻觉、位置编码、合成数据、提示工程、SLMs ...
<!-- - Prompt Engineering放在LLM调用API的实践课程里面，提供openai api和deepseek api两个版本的colab notebook -->

<!-- **Suggested Readings:** -->
<!-- - [Readings 1](http://example.com)
- [Readings 2](http://example.com) -->
