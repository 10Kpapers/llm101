---
type: lecture
date: 2024-11-16T8:00:00+4:30
title: 什么是语言模型(任务)?
tldr: "关于NLP的一些基础知识：NLP简介、了解常见的NLP任务、词向量(word2vec)、预训练模型(ELMo、BERT)发展历程"
thumbnail: /static_files/presentations/lec.jpg

# 添加slides附件
links: 
     - url: /static_files/slides/第一章2024.11.28.pdf
       name: "第一章slides"

     - url: https://www.bilibili.com/video/BV1WmBvYGEYU/?spm_id_from=333.999.0.0
       name: "第一节视频(bilibili)"
     - url: https://www.bilibili.com/video/BV1KLzPYoEbh/?spm_id_from=333.999.0.0
       name: "第二节视频(bilibili)"
     - url: https://www.bilibili.com/video/BV127zKYAExE/?spm_id_from=333.999.0.0
       name: "第三节视频(bilibili)"
#     - url: /static_files/presentations/code.zip
#       name: codes
#     - url: https://google.com
#       name: slides
---

* 关于NLP的一些基础知识：NLP简介、了解常见的NLP任务、词向量(word2vec)、预训练模型(ELMo、BERT)发展历程
* 回顾NLP中语言模型任务的发展历史：N-gram LM、FFN LM、RNN LM、GPT
* 理解向量(Embedding)的重要性，[代码链接](https://github.com/MachineLovesLearning/llm101_codes)：
  - 词向量可视化
  - 调用SiliconFlow Embedding API 计算句子向量的余弦相似度
  - 基于transformers BERT fine-tuning的中文文本分类
  - 基于arXiv论文数据 + SiliconFlow API + faiss + streamlit 构建论文搜索引擎demo
* 一点数学计算：
  - 斯坦福CS224N 作业2中[Understanding word2vec](https://web.stanford.edu/class/cs224n/assignments/a2.pdf)
  - 普林斯顿 COS 484 作业1中[LM和ppl理解](https://princeton-nlp.github.io/cos484/assignments/a1.pdf)


<!-- **Suggested Readings:** -->
<!-- - [Readings 1](http://example.com) -->
<!-- - [Readings 2](http://example.com) -->
