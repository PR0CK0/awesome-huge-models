<!-- omit in toc -->

# awesome-huge-models [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

A collection of AWESOME things about HUGE AI models.

There is a trend of training large-scale deep learning models (w.r.t. params, dataset, FLOPs) led by big companies. These models achieve the SoTA performance at a high price, with bags of training tricks and distributed training systems. Keeping an eye on this trend informs us of the current boundaries of AI models. [[Intro in Chinese](https://zhuanlan.zhihu.com/p/529863941)]

To support the open source process of LLM, we highlight the open-sourced LLM models here:

> LLaMA-65B, GLM-130B, BLOOM-176B, OPT-175B, T5-11B, UL2-20B, RWKV-14B, Cerabras-GPT-13B, Dolly-12B.

<!-- omit in toc -->

## Contents

- [awesome-huge-models ](#awesome-huge-models-)
  - [Contents](#contents)
  - [Survey](#survey)
  - [Models](#models)
    - [Language Model](#language-model)
    - [Vision Models](#vision-models)
    - [Reinforcement Learning](#reinforcement-learning)
    - [Speech](#speech)
    - [Science](#science)
  - [Distributed Training Framework](#distributed-training-framework)
    - [PyTorch Ecosystem](#pytorch-ecosystem)
    - [XLA Ecosystem](#xla-ecosystem)
    - [Other Frameworks](#other-frameworks)
    - [Inference Frameworks](#inference-frameworks)
    - [Recommendation Training Framework](#recommendation-training-framework)
  - [Keys Explanations](#keys-explanations)

## Survey

- [A Dive into Vision-Language Models](https://huggingface.co/blog/vision_language_pretraining)
- [Compute Trends Across Three Eras of Machine Learning](https://arxiv.org/abs/2202.05924) [[chart](https://ourworldindata.org/grapher/ai-training-computation)]
- [A Roadmap to Big Model](https://arxiv.org/abs/2203.14101)
- [On the Opportunities and Risk of Foundation Models](https://arxiv.org/abs/2108.07258)
- [Pre-Trained Models: Past, Present and Future](https://arxiv.org/abs/2106.07139)

<p align="center">
    <img src="img/ai-training-computation-2.png" alt="Big models in NLP" width="460"/>
</p >

## Models

### Language Model

- **StableVicuna** [[Vicuna]](https://vicuna.lmsys.org/) Apr. 2023 [[open]](https://github.com/lm-sys/FastChat)

```yaml
  Field: Language
  Params: 13B
  Training Data: ShareGPT
  ```
  
- **StableLM** [[Stability AI]](https://github.com/stability-AI/stableLM/) Apr. 2023 [[open]](https://huggingface.co/stabilityai)

  ```yaml
  Field: Language
  Params: 3B, 7B, 15B, 30B, 65B, 175B
  Training Data: The Pile (1.5t tokens)
  ```

- **Dolly 2.0** [[EleutherAI]](https://huggingface.co/databricks/dolly-v2-12b) Apr. 2023 [[open]]()  

  ```yaml
  Field: Language
  Params: 12B
  Training Data: databricks-dolly-15k
  ```

- **Cerabras-GPT** [[Cerabras]]() Mar. 2023 [[open]](https://huggingface.co/cerebras/Cerebras-GPT-13B)  
  Training Compute-Optimal Large Language Models [[preprint]](https://arxiv.org/abs/2203.15556)  

  ```yaml
  Field: Language
  Params: 13B
  Training Data: (371B tokens)
  ```

- **GPT-4** [[OpenAI]](https://openai.com/product/gpt-4) Mar. 2023 [close]  
   GPT-4 Technical Report [[Preprint]](https://cdn.openai.com/papers/gpt-4.pdf)

  ```yaml
  Field: Language-Vision
  ```

- **LLaMa** [[Meta]]() Feb. 2023 [[open]](https://github.com/facebookresearch/llama)  
   Open and Efficient Foundation Language Models [[Preprint]](https://arxiv.org/pdf/2302.13971v1.pdf)

  ```yaml
  Field: Language
  Params: 65B
  Training Data: 4TB (1.4T tokens)
  Training Cost: 1,022,362 (2048 80G-A100 x 21 days)
  Training Power Consumption: 449 MWh
  ```

- **RWKV-4-14B** [[Personal]]() Dec. 2022 [[open]](https://github.com/BlinkDL/RWKV-LM)

  ```yaml
  Field: Language
  Params: 14B
  Training Data: (332B tokens)
  ```

- **AnthropicLM** [[Anthropic]]() Dec. 2022 [close]  
   Constitutional AI: Harmlessness from AI Feedback

  ```yaml
  Field: Language
  Params: 52B
  ```

- **BLOOM** [[BigScience]]() Nov. 2022 [[open]](https://huggingface.co/bigscience/bloom)  
   A 176B-Parameter Open-Access Multilingual Language Model [[Preprint]](https://arxiv.org/pdf/2211.05100.pdf)

  ```yaml
  Field: Language
  Params: 176B
  Training Data: 174GB (336B tokens)
  Training Cost: 1M A100 GPU hours = 384 80G-A100 x 4 months
  Training Power Consumption: 475 MWh
  Training Framework: Megatron + Deepspeed
  ```
  
- **Galactica** [[Meta]]() Nov. 2022 [[open]](https://huggingface.co/facebook/galactica-1.3b)
  A scientific language model trained on over 48 million scientific texts [[Preprint]](https://arxiv.org/pdf/2211.09085.pdf)
  
  ```yaml
  Field: Language
  Params: 125M, 1.3B, 6.7B, 30B, 120B
  ```

- **Pythia** [[EleutherAI]]() Oct. 2022 [[open]](https://github.com/EleutherAI/pythia)
  
  ```yaml
  Field: Language
  Params: 12B
  ```

- **GLM-130B** [[BAAI]](https://keg.cs.tsinghua.edu.cn/glm-130b/zh/posts/glm-130b/) Oct. 2022 [[open]](https://github.com/THUDM/GLM-130B)  
   GLM-130B: An Open Bilingual Pre-trained Model [[ICLR'23]](https://arxiv.org/pdf/2210.02414.pdf)

  ```yaml
  Field: Language
  Params: 130B
  Training Data: (400B tokens)
  Training Cost: 516,096 A100 hours = 768 40G-A100 x 28 days
  Training Framework: Megatron + Deepspeed
  ```

- **UL2** [[Google]]() May 2022 [[open]](https://huggingface.co/google/ul2)  
   Unifying Language Learning Paradigms [[Preprint]](https://arxiv.org/abs/2205.05131)

  ```yaml
  Field: Language
  Params: 20B (1T tokens)
  Training Data: 800GB
  Achitecture: En-De
  Training Framework: Jax + T5x
  ```

- **OPT** [[Meta]](https://ai.facebook.com/blog/democratizing-access-to-large-scale-language-models-with-opt-175b/) May 2022 [[open]](https://github.com/facebookresearch/metaseq)  
   OPT: Open Pre-trained Transformer Language Models [[Preprint]](https://arxiv.org/abs/2205.01068)

  ```yaml
  Field: Language
  Params: 175B
  Training Data: 800GB (180B tokens)
  Training Cost: 809,472 A100 hours =  992 80G-A100 x 34 days
  Training Power Consumption: 356 MWh
  Architecutre: De
  Training Framework: Megatron + Fairscale
  ```

- **PaLM** [[Google]](https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html) Apr. 2022 [close]  
   PaLM: Scaling Language Modeling with Pathways [[Preprint]](https://arxiv.org/abs/2204.02311)

  ```yaml
  Field: Language
  Params: 550B
  Training Data: 3TB (780B tokens)
  Training Cost: $10M (16,809,984 TPUv4core-hours, 64 days)
  Training petaFLOPs: 2.5B
  Architecture: De
  Training Framework: Jax + T5x
  ```

- **GPT-NeoX** [[EleutherAI]](https://blog.eleuther.ai/announcing-20b/) Apr. 2022 [[open]](https://github.com/EleutherAI/gpt-neox)  
   GPT-NeoX-20B: An Open-Source Autoregressive Language Model [[Preprint]](https://arxiv.org/abs/2204.06745)

  ```yaml
  Field: Language
  Params: 20B
  Training Data: 525GiB
  Training petaFLOPs: 93B
  Architecture: De
  Training Framework: Megatron + Fairscale
  ```

- **InstructGPT** [[OpenAI]]() Mar. 2022 [close]  
   Training language models to follow instructions with human feedback [[Preprint]](https://arxiv.org/abs/2203.02155)

  ```yaml
  Field: Language
  Params: 175B
  ```

- **Chinchilla** [[DeepMind]](https://www.deepmind.com/publications/an-empirical-analysis-of-compute-optimal-large-language-model-training) Mar. 2022 [close]  
   Training Compute-Optimal Large Language Models [[Preprint]](https://arxiv.org/abs/2203.15556)

  ```yaml
  Field: Language
  Params: 70B
  Training Data: 5.2TB (1.4T tokens)
  Training petaFLOPs: 580M
  Architecture: De
  ```

- **EVA 2.0** [[BAAI]](https://wudaoai.cn/model/detail/EVA) Mar. 2022 [[open]](https://openi.pcl.ac.cn/BAAI/WuDao-Model/src/branch/master)  
   EVA2.0: Investigating Open-Domain Chinese Dialogue Systems with Large-Scale Pre-Training [[Preprint]](https://arxiv.org/abs/2203.09313)

  ```yaml
  Field: Language (Dialogue)
  Params: 2.8B
  Training Data: 180G (1.4B samples, Chinese)
  ```

- **AlphaCode** [[DeepMind]](https://www.deepmind.com/blog/competitive-programming-with-alphacode) Mar. 2022 [close]  
   Competition-Level Code Generation with AlphaCode [[Preprint]](https://arxiv.org/abs/2203.07814)

  ```yaml
  Field: Code Generation
  Params: 41B
  Training Data: (967B tokens)
  Architecture: De
  ```

- **ST-MoE** [[Google]]() Feb. 2022 [close]  
   ST-MoE: Designing Stable and Transferable Sparse Expert Models [[Preprint]](https://arxiv.org/abs/2202.08906)

  ```yaml
  Field: Language
  Params: 296B
  Architecture: En-De, MoE
  ```

- **LaMDA** [[Google]](https://arxiv.org/abs/2201.08239) Jan. 2022 [close]  
   LaMDA: Language Models for Dialog Applications [[Preprint]](https://arxiv.org/abs/2201.08239)

  ```yaml
  Field: Language (Dialogue)
  Params: 137B
  Training Data: (1.56T words)
  Training petaFLOPs: 360M
  Architecture: De
  ```

- **ERNIE-ViLG** [[Baidu]](https://wenxin.baidu.com/wenxin/ernie-vilg) Dec. 2022 [close]  
   ERNIE-ViLG: Unified Generative Pre-training for Bidirectional Vision-Language Generation [[Preprint]](https://arxiv.org/abs/2112.15283)

  ```yaml
  Field: Image Generation (text to image)
  Params: 10B
  Training Data: (145M text-image pairs)
  Architecture: Transformer, dVAE + De
  ```

- **GLaM** [[Google]](https://ai.googleblog.com/2021/12/more-efficient-in-context-learning-with.html) Dec. 2021 [close]  
   GLaM: Efficient Scaling of Language Models with Mixture-of-Experts [[Preprint]](https://arxiv.org/abs/2112.06905)

  ```yaml
  Field: Language
  Params: 1.2T
  Architecture: De, MoE
  ```

- **Gopher** [[DeepMind]](https://www.deepmind.com/blog/language-modelling-at-scale-gopher-ethical-considerations-and-retrieval) Dec. 2021 [close]  
   Scaling Language Models: Methods, Analysis & Insights from Training Gopher [[Preprint]](https://arxiv.org/abs/2112.11446)

  ```yaml
  Field: Language
  Params: 280B
  Training Data: 1.3TB (300B tokens)
  Training petaFLOPs: 630M
  Architecture: De
  ```

- **Yuan 1.0** [[inspur]](https://air.inspur.com/home) Oct. 2021 [close]  
   Yuan 1.0: Large-Scale Pre-trained Language Model in Zero-Shot and Few-Shot Learning [[Preprint]](https://arxiv.org/abs/2110.04725)

  ```yaml
  Field: Language
  Params: 245B
  Training Data: 5TB (180B tokens, Chinese)
  Training petaFLOPs: 410M
  Architecture: De, MoE
  ```

- **MT-NLG** [[Microsoft, Nvidia]](https://www.microsoft.com/en-us/research/blog/using-deepspeed-and-megatron-to-train-megatron-turing-nlg-530b-the-worlds-largest-and-most-powerful-generative-language-model/) Oct. 2021 [close]  
   Using DeepSpeed and Megatron to Train Megatron-Turing NLG 530B, A Large-Scale Generative Language Model [[Preprint]](https://arxiv.org/abs/2201.11990)

  ```yaml
  Field: Language
  Params: 530B
  Training Data: (339B tokens)
  Training petaFLOPs: 1.4B
  Architecture: De
  ```

- **Plato-XL** [[Baidu]](http://research.baidu.com/Blog/index-view?id=163) Sept. 2021 [close]  
   PLATO-XL: Exploring the Large-scale Pre-training of Dialogue Generation [[Preprint]](https://arxiv.org/abs/2109.09519)

  ```yaml
  Field: Language (Dialogue)
  Params: 11B
  Training Data: (1.2B samples)
  ```

- **Jurassic-1** [[AI21 Labs]](https://www.zdnet.com/article/watch-out-gpt-3-here-comes-ai21s-jurassic-language-model/) Aug. 2021 [close]  
   Jurassic-1: Technical Details and Evaluation [[Preprint]](https://uploads-ssl.webflow.com/60fd4503684b466578c0d307/61138924626a6981ee09caf6_jurassic_tech_paper.pdf)

  ```yaml
  Field: Language
  Params: 178B
  Training petaFLOPs: 370M
  Architecture: De
  ```

- **Codex** [[OpenAI]](https://openai.com/blog/openai-codex/) July 2021 [close]  
   Evaluating Large Language Models Trained on Code [[Preprint]](https://arxiv.org/abs/2107.03374)

  ```yaml
  Field: Code Generation
  Params: 12B
  Training Data: 159GB
  Architecture: De
  ```

- **ERNIE 3.0** [[Baidu]](https://wenxin.baidu.com/wenxin/ernie) July 2021 [close]  
   ERNIE 3.0: Large-scale Knowledge Enhanced Pre-training for Language Understanding and Generation [[Preprint]](https://arxiv.org/abs/2107.02137)

  ```yaml
  Field: Language
  Params: 10B
  Training Data: 4TB (375B tokens, with knowledge graph)
  Architecture: En
  Objective: MLM
  ```

- **CPM-2** [[BAAI]]() June 2021 [[open]](https://openi.pcl.ac.cn/BAAI/WuDao-Model/src/branch/master)  
   CPM-2: Large-scale Cost-effective Pre-trained Language Models [[Preprint]](https://arxiv.org/abs/2106.10715)

  ```yaml
  Field: Language
  Params: 198B
  Training Data: 2.6TB (Chinese 2.3TB, English 300GB)
  Architecture: En-De
  Objective: MLM
  ```

- **HyperClova** [[Naver]](https://www.navercorp.com/promotion/pressReleasesView/30546) May 2021 [close]  
   What Changes Can Large-scale Language Models Bring? Intensive Study on HyperCLOVA: Billions-scale Korean Generative Pretrained Transformers [[Preprint]](https://arxiv.org/abs/2109.04650v1)

  ```yaml
  Field: Language
  Params: 82B
  Training Data: (562B tokens, Korean)
  Training petaFLOPs: 63B
  Architecture: De
  ```

- **ByT5** [[Google]]() May 2021 [[open]](https://github.com/google-research/byt5)  
   ByT5: Towards a token-free future with pre-trained byte-to-byte models [[TACL'22]](https://arxiv.org/abs/2105.13626)

  ```yaml
  Field: Language
  Params: 13B
  Training Data: (101 languages)
  Architecture: En-De
  ```

- **PanGu-α** [[Huawei]]() Apr. 2021 [close]  
   PanGu-α: Large-scale Autoregressive Pretrained Chinese Language Models with Auto-parallel Computation [[Preprint]](https://arxiv.org/abs/2104.12369)

  ```yaml
  Field: Language
  Params: 200B
  Training Data: 1.1TB (Chinese)
  Training petaFLOPs: 58M
  Architecture: De
  ```

- **mT5** [[Google]]() Mar. 2021 [[open]](https://github.com/google-research/multilingual-t5)  
   mT5: A massively multilingual pre-trained text-to-text transformer [[Preprint]](https://arxiv.org/abs/2010.11934)

  ```yaml
  Field: Language
  Params: 13B
  Training Data: (101 languages)
  Architecture: En-De
  ```

- **WuDao-WenHui** [[BAAI]]() Mar. 2021 [[open]](https://openi.pcl.ac.cn/BAAI/WuDao-Model/src/branch/master/Transformer-XL)

  ```yaml
  Field: Language
  Params: 2.9B
  Training Data: 303GB (Chinese)
  ```

- **GLM** [[BAAI]]() Mar. 2021 [[open]](https://openi.pcl.ac.cn/BAAI/WuDao-Model/src/branch/master/GLM)  
   GLM: General Language Model Pretraining with Autoregressive Blank Infilling [[Preprint]](https://arxiv.org/abs/2103.10360)

  ```yaml
  Field: Language
  Params: 10B
  Architecture: De
  ```

- **Switch Transformer** [[Google]]() Jan. 2021 [[open]](https://github.com/google-research/t5x)  
   Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity [[Preprint]](https://arxiv.org/abs/2101.03961)

  ```yaml
  Field: Language
  Params: 1.6T
  Training Data: 750GB
  Training petaFLOPs: 82M
  Architecture: En-De, MoE
  Objective: MLM
  ```

- **CPM** [[BAAI]]() Dec. 2020 [[open]](https://github.com/TsinghuaAI/CPM)  
   CPM: A Large-scale Generative Chinese Pre-trained Language Model [[Preprint]](https://arxiv.org/abs/2012.00413)

  ```yaml
  Field: Language
  Params: 2.6B
  Training Data: 100G (Chinese)
  Training petaFLOPs: 1.8M
  Architecture: De
  Objective: LTR
  ```

- **GPT-3** [[OpenAI]](https://openai.com/api/) May 2020 [close]  
   Language Models are Few-Shot Learners [[NeurIPS'20]](https://papers.nips.cc/paper/2020/file/1457c0d6bfcb4967418bfb8ac142f64a-Paper.pdf)

  ```yaml
  Field: Language
  Params: 175B
  Training Data: 45TB (680B Tokens)
  Training Time: 95 A100 GPU years (835584 A100 GPU hours, 355 V100 GPU years)
  Training Cost: $4.6M
  Training petaFLOPs: 310M
  Architecture: De
  Obective: LTR
  ```

- **Blender** [[Meta]](https://ai.facebook.com/blog/blender-bot-2-an-open-source-chatbot-that-builds-long-term-memory-and-searches-the-internet/) Apr. 2020 [[close]](https://huggingface.co/facebook/blenderbot-90M?text=Hey+my+name+is+Thomas%21+How+are+you%3F)  
   Recipes for building an open-domain chatbot [[Preprint]](https://arxiv.org/abs/2004.13637)

  ```yaml
  Field: Language (Dialogue)
  Params: 9.4B
  ```

- **T-NLG** [[Microsoft]](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/) Feb. 2020 [close]

  ```yaml
  Field: Language
  Params: 17B
  Training petaFLOPs: 16M
  Architecture: De
  Obective: LTR
  ```

- **Meena** [[Google]](https://ai.googleblog.com/2020/01/towards-conversational-agent-that-can.html) Jan. 2020 [close]  
   Towards a Human-like Open-Domain Chatbot [[Preprint]](https://arxiv.org/abs/2001.09977)

  ```yaml
  Field: Language (Dialogue)
  Params: 2.6B
  Training Data: 341GB (40B words)
  Training petaFLOPs: 110M
  ```

- **DialoGPT** [[Microsoft]](https://www.microsoft.com/en-us/research/project/large-scale-pretraining-for-response-generation/) Nov. 2019 [[open]](https://github.com/microsoft/DialoGPT)  
   DialoGPT: Large-Scale Generative Pre-training for Conversational Response Generation [[ACL'20]](https://arxiv.org/abs/1911.00536)

  ```yaml
  Field: Language (Dialogue)
  Params: 762M
  Training Data: (147M conversation)
  Architecture: De
  ```

- **T5** [[Google]](https://ai.googleblog.com/2020/02/exploring-transfer-learning-with-t5.html) Oct. 2019 [[open]](https://github.com/google-research/text-to-text-transfer-transformer)  
   Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer [[JMLR'19]](https://arxiv.org/abs/1910.10683)

  ```yaml
  Field: Language
  Params: 11B
  Training Data: 800GB
  Training Cost: $1.5M
  Training petaFLOPs: 41M
  Architecture: En-De
  Obective: MLM
  ```

- **Megatron-LM** [[Nvidia]]() Sept. 2019 [[open]](https://github.com/NVIDIA/Megatron-LM)  
   Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism [[Preprint]](https://arxiv.org/abs/1909.08053)

  ```yaml
  Field: Language
  Params: 8.3B
  Training Data: 174 GB
  Training petaFLOPs: 9.1M
  Architecture: De
  Obective: LTR
  Training Framework: Megatron
  ```

- **Megatron-BERT** [[Nvidia]]() Sept. 2019 [[open]](https://github.com/NVIDIA/Megatron-LM)  
   Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism [[Preprint]](https://arxiv.org/abs/1909.08053)

  ```yaml
  Field: Language
  Params: 3.9B
  Training Data: 174 GB
  Training petaFLOPs: 57M
  Architecture: En
  Obective: MLM
  Training Framework: Megatron
  ```

- **RoBERTa** [[Meta]](https://ai.facebook.com/blog/roberta-an-optimized-method-for-pretraining-self-supervised-nlp-systems/) July 2019 [[open]](https://github.com/facebookresearch/fairseq)  
   RoBERTa: A Robustly Optimized BERT Pretraining Approach [[Preprint]](https://arxiv.org/abs/1907.11692)

  ```yaml
  Field: Language
  Params: 354M
  Training Data: 160GB
  Training Time: 1024 V100 GPU days
  Architecture: En
  Objective: MLM
  ```

- **XLNet** [[Google]]() June 2019 [[open]](https://github.com/zihangdai/xlnet)  
   XLNet: Generalized Autoregressive Pretraining for Language Understanding [[NeurIPS'19]](https://papers.nips.cc/paper/2019/hash/dc6a7e655d7e5840e66733e9ee67cc69-Abstract.html)

  ```yaml
  Field: Language
  Params: 340M
  Training Data: 113GB (33B words)
  Training Time: 1280 TPUv3 days
  Training Cost: $245k
  Architecture: En
  Objective: PLM
  ```

- **GPT-2** [[OpenAI]](https://openai.com/blog/better-language-models/) Feb. 2019 [[open]](https://github.com/openai/gpt-2)  
   Language Models are Unsupervised Multitask Learners [[Preprint]](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf)

  ```yaml
  Field: Language
  Params: 1.5B
  Training Data: 40GB (8M web pages)
  Training Cost: $43k
  Training petaFLOPs: 1.5M
  Architecture: De
  Objective: LTR
  ```

- **BERT** [[Google]]() Oct. 2018 [[open]](https://github.com/google-research/bert)  
   BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding [[NAACL'18]](https://arxiv.org/abs/1810.04805)

  ```yaml
  Field: Language
  Params: 330M
  Training Data: 16GB (3.3B words)
  Training Time: 64 TPUv2 days (280 V100 GPU days)
  Training Cost: $7k
  Training petaFLOPs: 290k
  Architecture: En
  Objective: MLM, NSP
  ```

- **GPT** [[OpenAI]](https://openai.com/blog/language-unsupervised/) June 2018 [open]
  Improving Language Understanding by Generative Pre-Training [[Preprint]](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf)

  ```yaml
  Field: Language
  Params: 117M
  Training Data: 1GB (7k books)
  Training petaFLOPs: 18k
  Architecture: De
  Objective: LTR
  ```

### Vision Models

- **MAE->WSP-2B** [[Meta]]() Mar. 2023 [close]  
   The effectiveness of MAE pre-pretraining for billion-scale pretraining

  ```yaml
  Field: Vision
  Params: 6.5B
  Training Data: (3B images)
  Architecture: Transformer
  Objective: MAE, Weakly-Supervised
  ```

- **OpenCLIP G/14** [[LAION]]() Mar. 2023 [[open]](https://huggingface.co/laion/CLIP-ViT-g-14-laion2B-s12B-b42K)

  ```yaml
  Field: Vision-Language
  Params: 2.5B
  Training Data: (2B images)
  ```

- **ViT-22B** [[Google]]() Feb. 2023 [close]
  Scaling Vision Transformers to 22 Billion Parameters

  ```yaml
  Field: Vision
  Params: 22B
  Training Data: (4B images)
  Architecture: Transformer
  Objective: Supervised
  ```

- **InternImage-G** [[Shanghai AI Lab]](https://github.com/OpenGVLab/InternImage) Nov. 2022 [[open]](https://github.com/OpenGVLab/InternImage)
  InternImage: Exploring Large-Scale Vision Foundation Models with Deformable Convolutions [[CVPR'23 Highlight]](https://arxiv.org/abs/2211.05778)

  ```yaml
  Field: Vision
  Params: 3B
  Architecture: CNN
  Core Operator: Deformable Convolution v3
  ```

- **Stable Diffusion** [[Stability AI]]() Aug. 2022 [[open]]()

  ```yaml
  Field: Image Generation (text to image)
  Params: 890M
  Training Data: (5B images)
  Architecture: Transformer, Diffusion
  ```

- **Imagen** [[Google]](https://imagen.research.google/) May 2022  
   Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding [[Preprint]](https://arxiv.org/abs/2205.11487)

  ```yaml
  Field: Image Generation (text to image)
  Text Encoder: T5
  Image Decoder: Diffusion, Upsampler
  ```

- **Flamingo** [[DeepMind]]() Apr. 2022 [close]  
   Flamingo: a Visual Language Model for Few-Shot Learning [[Preprint]](https://arxiv.org/abs/2204.14198)

  ```yaml
  Field: Vision-Language
  Params: 80B
  ```

- **DALL·E 2** [[OpenAI]](https://openai.com/dall-e-2/) Apr. 2022  
   Hierarchical Text-Conditional Image Generation with CLIP Latents [[Preprint]](https://cdn.openai.com/papers/dall-e-2.pdf)

  ```yaml
  Field: Image Generation (text to image)
  Text Encoder: GPT2 (CLIP)
  Image Encoder: ViT (CLIP)
  Image Decoder: Diffusion, Upsampler
  ```

- **BaGuaLu** [[BAAI, Alibaba]]() Apr. 2022  
   BaGuaLu: targeting brain scale pretrained models with over 37 million cores [[PPoPP'22]](https://keg.cs.tsinghua.edu.cn/jietang/publications/PPOPP22-Ma%20et%20al.-BaGuaLu%20Targeting%20Brain%20Scale%20Pretrained%20Models%20w.pdf)

  ```yaml
  Field: Vision-Language
  Params: 174T
  Architecture: M6
  ```

- **SEER** [[Meta]]() Feb. 2022 [[open]](https://github.com/facebookresearch/vissl)  
   Vision Models Are More Robust And Fair When Pretrained On Uncurated Images Without Supervision [[Preprint]](https://arxiv.org/abs/2202.08360v2)

  ```yaml
  Field: Vision
  Params: 10B
  Training Data: (1B images)
  Architecture: Convolution
  Objective: SwAV
  ```

- **ERNIE-ViLG** [[Baidu]](https://wenxin.baidu.com/wenxin/ernie-vilg) Dec. 2021  
   ERNIE-ViLG: Unified Generative Pre-training for Bidirectional Vision-Language Generation [[Preprint]](https://arxiv.org/abs/2112.15283)

  ```yaml
  Field: Image Generation (text to image)
  Params: 10B
  Training Data: (145M text-image pairs)
  Architecture: Transformer, dVAE + De
  ```

- **NUWA** [[Microsoft]]() Nov. 2021 [[open]](https://github.com/microsoft/NUWA)  
   NÜWA: Visual Synthesis Pre-training for Neural visUal World creAtion [[Preprint]](https://arxiv.org/abs/2111.12417)

  ```yaml
  Field: Vision-Language
  Generatioon: Image, Video
  Params: 870M
  ```

- **SwinV2-G** [[Google]]() Nov. 2021 [[open]](https://github.com/microsoft/Swin-Transformer)  
   Swin Transformer V2: Scaling Up Capacity and Resolution [[CVPR'22]](https://arxiv.org/abs/2111.09883v2)

  ```yaml
  Field: Vision
  Params: 3B
  Training Data: 70M
  Architecture: Transformer
  Objective: Supervised
  ```

- **Zidongtaichu** [[CASIA]](http://www.ia.cas.cn/xwzx/kydt/202109/t20210927_6215538.html) Sept. 2021 [close]

  ```yaml
  Field: Image, Video, Language, Speech
  Params: 100B
  ```

- **ViT-G/14** [[Google]]() June 2021  
   Scaling Vision Transformers [[Preprint]](https://arxiv.org/abs/2106.04560)

  ```yaml
  Field: Vision
  Params: 1.8B
  Training Data: (300M images)
  Training petaFLOPs: 3.4M
  Architecture: Transformer
  Objective: Supervised
  ```

- **CoAtNet** [[Google]](https://ai.googleblog.com/2021/09/toward-fast-and-accurate-neural.html) June 2021 [[open]](https://github.com/chinhsuanwu/coatnet-pytorch)  
   CoAtNet: Marrying Convolution and Attention for All Data Sizes [[NeurIPS'21]](https://arxiv.org/abs/2106.04803)

  ```yaml
  Field: Vision
  Params: 2.4B
  Training Data: (300M images)
  Architecture: Transformer, Convolution
  Objective: Supervised
  ```

- **V-MoE** [[Google]](https://ai.googleblog.com/2022/01/scaling-vision-with-sparse-mixture-of.html) June 2021  
   Scaling Vision with Sparse Mixture of Experts [[NeurIPS'21]](https://proceedings.neurips.cc//paper/2021/file/48237d9f2dea8c74c2a72126cf63d933-Paper.pdf)

  ```yaml
  Field: Vision
  Params: 15B
  Training Data: (300M images)
  Training Time: 16.8k TPUv3 days
  Training petaFLOPs: 33.9M
  Architecture: Transformer, MoE
  Objective: Supervised
  ```

- **CogView** [[BAAI, Alibaba]](https://wudao.aminer.cn/CogView/index.html) May 2021 [</>](https://github.com/THUDM/CogView)  
   CogView: Mastering Text-to-Image Generation via Transformers [[NeurIPS'21]](https://arxiv.org/abs/2105.13290)

  ```yaml
  Field: Vision-Language
  Params: 4B
  Training Data: (30M text-image pairs)
  Training petaFLOPs: 27M
  Image Encoder: VAE
  Text Encoder & Image Decoder: GPT2
  ```

- **M6** [[Alibaba]](https://m6.aliyun.com/#/) Mar. 2021  
   M6: A Chinese Multimodal Pretrainer [[Preprint]](https://arxiv.org/abs/2103.00823)

  ```yaml
  Field: Vision-Language
  Params: 10T
  Training Data: 300G Texts + 2TB Images
  Training petaFLOPs: 5.5M
  Fusion: Single-stream
  Objective: MLM, IC
  ```

- **DALL·E** [[OpenAI]](https://openai.com/blog/dall-e/) Feb. 2021  
   Zero-Shot Text-to-Image Generation [[ICML'21]](https://arxiv.org/abs/2102.12092)

  ```yaml
  Field: Image Generation (text to image)
  Params: 12B
  Training Data: (250M text-images pairs)
  Training petaFLOPs: 47M
  Image Encoder: dVAE
  Text Encoder & Image Decoder: GPT2
  ```

- **CLIP** [[OpenAI]](https://openai.com/blog/clip/) Jan. 2021  
   Learning Transferable Visual Models From Natural Language Supervision [[ICML'22]](https://arxiv.org/abs/2103.00020)

  ```yaml
  Field: Vision-Language
  Training Data: 400M text-image pairs
  Training petaFLOPs: 11M
  Image Encoder: ViT
  Text Encoder: GPT-2
  Fusion: Dual Encoder
  Objective: CMCL
  ```

- **ViT-H/14** [[Google]](https://ai.googleblog.com/2020/12/transformers-for-image-recognition-at.html) Oct. 2020 [[open]](https://github.com/google-research/vision_transformer)  
   An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale [[ICLR'20]](https://arxiv.org/abs/2010.11929)

  ```yaml
  Field: Vision
  Params: 632M
  Training Data: (300M images)
  Training petaFLOPs: 13M
  Architecture: Transformer
  Objective: Supervised
  ```

- **iGPT-XL** [[OpenAI]](https://openai.com/blog/image-gpt/) June 2020 [[open]](https://github.com/openai/image-gpt)  
   Generative Pretraining From Pixels [[ICML'20]](https://proceedings.mlr.press/v119/chen20s.html)

  ```yaml
  Field: Image Generation
  Params: 6.8B
  Training Data: (1M images)
  Training petaFLOPs: 33M
  Architecture: Transformer, De
  ```

- **BigGAN-deep** [[DeepMind]]() Sept. 2018 [[open]](https://github.com/ajbrock/BigGAN-PyTorch)  
   Large Scale GAN Training for High Fidelity Natural Image Synthesis [[ICLR'19]](https://arxiv.org/abs/1809.11096)

  ```yaml
  Field: Image Generation
  Params: 158M
  Training Data: (300M images)
  Training petaFLOPs: 3M
  Architecture: Convolution, GAN
  Resolution: 512x512
  ```

### Reinforcement Learning

- **PaLM-E** [[Google]](https://palm-e.github.io/) March 2023 [close]  
   PaLM-E: An Embodied Multimodal Language Model [[Preprint]](https://palm-e.github.io/assets/palm-e.pdf)

  ```yaml
  Field: Reinforcement Learning
  Params: 562B (540B LLM + 22B Vi)
  ```

- **Gato** [[DeepMind]](https://www.deepmind.com/publications/a-generalist-agent) May 2022 [close]  
   A Generalist Agent [[Preprint]](https://arxiv.org/abs/2205.06175)

  ```yaml
  Field: Reinforcement Learning
  Params: 1.2B
  Training Data: (604 Tasks)
  Objective: Supervised
  ```

### Speech

- **USM** [[Google]](https://sites.research.google/usm/) Mar. 2023 [close]  
  Google USM: Scaling Automatic Speech Recognition Beyond 100 Languages [[Preprint]](https://arxiv.org/pdf/2303.01037v2.pdf)

  ```yaml
  Field: Speech
  Params: 2B
  Training Data: 12,000,000 hours
  ```

- **Whisper** [[OpenAI]](https://openai.com/research/whisper) Sept. 2022 [[close]](https://github.com/openai/whisper)  
   Robust Speech Recognition via Large-Scale Weak Supervision [[Preprint]](https://arxiv.org/pdf/2212.04356.pdf)

  ```yaml
  Field: Speech
  Params: 1.55B
  Training Data: 680,000 hours
  Objective: Weakly Supervised
  ```

- **HuBERT** [[Meta]](https://ai.facebook.com/blog/hubert-self-supervised-representation-learning-for-speech-recognition-generation-and-compression/) June 2021 [[open]](https://github.com/facebookresearch/fairseq/tree/main/examples/hubert)  
   HuBERT: Self-Supervised Speech Representation Learning by Masked Prediction of Hidden Units [[Preprint]](https://arxiv.org/abs/2106.07447)

  ```yaml
  Field: Speech
  Params: 1B
  Training Data: 60,000 hours
  Objective: MLM
  ```

- **wav2vec 2.0** [[Meta]]() Oct. 2020 [[open]](https://github.com/facebookresearch/fairseq/tree/main/examples/wav2vec)  
   wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations [[NeurIPS'20]](https://arxiv.org/abs/2006.11477)

  ```yaml
  Field: Speech
  Params: 317M
  Training Data: 50,000 hours
  Training petaFLOPs: 430M
  Objective: MLM
  ```

- **DeepSpeech 2** [[Meta]]() Dec. 2015 [[open]](https://github.com/PaddlePaddle/PaddleSpeech)  
   Deep Speech 2: End-to-End Speech Recognition in
  English and Mandarin [[ICML'15]](https://arxiv.org/pdf/1512.02595.pdf)

      ```yaml
      Field: Speech
      Params: 300M
      Training Data: 21,340 hours
      ```

### Science

- **AlphaFold 2** [[DeepMind]](https://www.deepmind.com/research/highlighted-research/alphafold) July 2021 [[open]](https://github.com/deepmind/alphafold)  
   Highly accurate protein structure prediction with AlphaFold [[Nature]](https://www.nature.com/articles/s41586-021-03819-2)

  ```yaml
  Field: Biology
  Params: 21B
  Training petaFLOPs: 100k
  ```

## Distributed Training Framework

> Deep Learning frameworks supportting distributed training are marked with \*.

### PyTorch Ecosystem

- **Accelerate** [[Huggingface]]() Oct. 2020 [[open]](https://github.com/huggingface/accelerate)
- **Hivemind** Aug. 2020 [[open]](https://github.com/learning-at-home/hivemind)  
  Towards Crowdsourced Training of Large Neural Networks using Decentralized Mixture-of-Experts [[Preprint]](https://arxiv.org/abs/2002.04013)
- **FairScale** [[Meta]]() July 2020 [[open]](https://github.com/facebookresearch/fairscale)
- **DeepSpeed** [[Microsoft]](https://www.microsoft.com/en-us/research/project/deepspeed/) Oct. 2019 [[open]](https://github.com/microsoft/DeepSpeed)  
   ZeRO: Memory Optimizations Toward Training Trillion Parameter Models [[SC'20]](https://arxiv.org/abs/1910.02054)
- **Megatron** [[Nivida]]() Sept. 2019 [[open]](https://github.com/NVIDIA/Megatron-LM)  
   Megatron: Training Multi-Billion Parameter Language Models Using Model Parallelism [[Preprint]](https://arxiv.org/abs/1909.08053)
- **PyTorch\*** [[Meta]](https://pytorch.org/) Sept. 2016 [[open]](https://github.com/pytorch/pytorch)  
   PyTorch: An Imperative Style, High-Performance Deep Learning Library [[NeurIPS'19]](http://papers.neurips.cc/paper/9015-pytorch-an-imperative-style-high-performance-deep-learning-library.pdf)

### XLA Ecosystem

- **T5x** [[Google]]() Mar. 2022 [[open]](https://github.com/google-research/t5x)  
  Scaling Up Models and Data with 𝚝𝟻𝚡 and 𝚜𝚎𝚚𝚒𝚘 [[Preprint]](https://arxiv.org/abs/2203.17189)
- **Alpa** [[Google]]() Jan. 2022 [[open]](https://github.com/alpa-projects/alpa)  
  Alpa: Automating Inter- and Intra-Operator Parallelism for Distributed Deep Learning [[OSDI'22]](https://arxiv.org/pdf/2201.12023.pdf)
- **Pathways** [[Google]](https://blog.google/technology/ai/introducing-pathways-next-generation-ai-architecture/) Mar. 2021 [close]  
   Pathways: Asynchronous Distributed Dataflow for ML [[Preprint]](https://arxiv.org/abs/2203.12533)
- **Colossal-AI** [[HPC-AI TECH]](https://colossalai.org/) Nov. 2021 [[open]](https://github.com/hpcaitech/ColossalAI)  
   Colossal-AI: A Unified Deep Learning System For Large-Scale Parallel Training [[Preprint]](https://arxiv.org/abs/2110.14883)
- **GShard** [[Google]](https://arxiv.org/abs/2006.16668) June 2020  
   GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding [[Preprint]](https://arxiv.org/abs/2006.16668)
- **Jax\*** [Google]() Oct 2019 [[open]](https://github.com/google/jax)
- **Mesh Tensorflow** [[Google]]() Nov. 2018 [[open]](https://github.com/tensorflow/mesh)
- **Horovod** [[Uber]](https://horovod.ai/) Feb. 2018 [[open]](https://github.com/horovod/horovod)  
   Horovod: fast and easy distributed deep learning in TensorFlow [[Preprint]](https://arxiv.org/abs/1802.05799)
- **Tensorflow\*** [[Google]](https://www.tensorflow.org/) Nov. 2015 [[open]](https://github.com/tensorflow/tensorflow)  
   TensorFlow: A system for large-scale machine learning [[OSDI'16]](https://www.usenix.org/system/files/conference/osdi16/osdi16-abadi.pdf)

### Other Frameworks

- **OneFlow\*** [[OneFlow]](https://docs.oneflow.org/master/index.html) July 2020 [[open]](https://github.com/OneFlow-Inc/oneflow)  
   OneFlow: Redesign the Distributed Deep Learning Framework from Scratch [[Preprint]](https://arxiv.org/abs/2110.15032)
- **MindSpore\*** [[Huawei]](https://e.huawei.com/en/products/cloud-computing-dc/atlas/mindspore) Mar. 2020 [[open]](https://github.com/mindspore-ai/mindspore)
- **PaddlePaddle\*** [[Baidu]](https://www.paddlepaddle.org.cn/) Nov. 2018 [[open]](https://github.com/PaddlePaddle/Paddle)  
   End-to-end Adaptive Distributed Training on PaddlePaddle [[Preprint]](https://arxiv.org/abs/2112.02752)
- **Ray** [[Berkeley]]() Dec. 2017 [[open]]([OSDI'17](https://github.com/ray-project/ray))  
   Ray: A Distributed Framework for Emerging AI Applications [[OSDI'17]](https://arxiv.org/pdf/1712.05889.pdf)

### Inference Frameworks

- Petals [[BigScience]]() Dec. 2022 [[open]](https://github.com/bigscience-workshop/petals)
- FlexGen [[Stanford, Berkerley, CMU, etc.]]() May 2022 [[open]](https://github.com/FMInference/FlexGen)
- FastTransformer [[NVIDIA]]() Apr. 2021 [[open]](https://github.com/NVIDIA/FasterTransformer)
- MegEngine [[MegEngine]](https://www.megengine.org.cn/) Mar. 2020
- DeepSpeed-Inference [[Microsoft]](https://www.microsoft.com/en-us/research/project/deepspeed/) Oct. 2019 [[open]](https://github.com/microsoft/DeepSpeed)
- MediaPipe [[Google]](https://google.github.io/mediapipe/) July 2019 [[open]](https://github.com/google/mediapipe)
- TensorRT [[Nvidia]]() Jun 2019 [[open]](https://github.com/NVIDIA/TensorRT)
- MNN [[Alibaba]]() May 2019 [[open]](https://github.com/alibaba/MNN)
- OpenVINO [[Intel]](https://docs.openvino.ai/latest/index.html) Oct. 2019 [[open]](https://github.com/openvinotoolkit/openvino)
- ONNX [[Linux Foundation]](https://onnx.ai/) Sep 2017 [[open]](https://github.com/onnx/onnx)
- ncnn [[Tencent]]() July 2017 [[open]](https://github.com/Tencent/ncnn)

### Recommendation Training Framework

- **HET** [[Tencent]]() Dec. 2021  
   HET: Scaling out Huge Embedding Model Training via Cache-enabled Distributed Framework [[VLDB'22]](https://arxiv.org/abs/2112.07221)
- **Persia** [[Kuaishou]]() Nov. 2021  
   Persia: An Open, Hybrid System Scaling Deep Learning-based Recommenders up to 100 Trillion Parameters [[Preprint]](https://arxiv.org/abs/2111.05897)

  ```yaml
  Embeddings Params: 100T
  ```

- **ZionEX** [[Meta]]() Apr. 2021  
   Software-Hardware Co-design for Fast and Scalable Training of Deep Learning Recommendation Models [[ISCA'21]](https://arxiv.org/abs/2104.05158)

  ```yaml
  Embeddings Params: 10T
  ```

- **ScaleFreeCTR** [[Huawei]]() Apr. 2021  
   ScaleFreeCTR: MixCache-based Distributed Training System for CTR Models with Huge Embedding Table [[SIGIR'21]](https://arxiv.org/abs/2104.08542)
- **Kraken** [[Kuaishou]]() Nov. 2020  
   Kraken: Memory-Efficient Continual Learning for Large-Scale Real-Time Recommendations [[SC'20]](http://storage.cs.tsinghua.edu.cn/papers/sc20-kraken.pdf/)
- **TensorNet** [[Qihoo360]]() Sept. 2020 [[open]](https://github.com/Qihoo360/tensornet)
- **HierPS** [[Baidu]]() Mar. 2020  
   Distributed Hierarchical GPU Parameter Server for Massive Scale Deep Learning Ads Systems [[MLSys'20]](https://arxiv.org/abs/2003.05622)
- **AIBox** [[Baidu]]() Oct. 2019  
   AIBox: CTR Prediction Model Training on a Single Node [[CIKM'20]](https://dl.acm.org/doi/pdf/10.1145/3357384.3358045)

  ```yaml
  Embeddings Params: 0.1T
  ```

- **XDL** [[Alibaba]]() Aug. 2019  
   XDL: an industrial deep learning framework for high-dimensional sparse data [[DLP-KDD'21]](https://dlp-kdd.github.io/dlp-kdd2019/assets/pdf/a6-jiang.pdf)

  ```yaml
  Embeddings Params: 0.01T
  ```

## Keys Explanations

- Company tags: the related company name. Other institudes may also involve in the job.
- Params: number of parameters of the largest model
- Training data size, training cost and training petaFLOPs may have some uncertainty.
- Training cost
  - TPUv2 hour: $4.5
  - TPUv3 hour: $8
  - V100 GPU hour: $0.55 (2022)
  - A100 GPU hoor: $1.10 (2022)
- Architecture
  - En: Encoder-based Language Model
  - De: Decoder-based Language Model
  - En-De=Encoder-Decoder-based Language Model
  - The above three architectures are powered with transformers.
  - MoE: Mixture of Experts
- Objective (See explanation in section 6–8 of [this paper](https://arxiv.org/pdf/2203.14101v3.pdf))
  - MLM: Masked Language Modeling
  - LTR: Left-To-Right Language Modeling
  - NSP: Next Sentence Prediction
  - PLM: Permuted Language Modeling
  - IC: Image Captioning
  - VLM: Vision Languauge Matching
  - CMCL: Cross-Modal Contrastive Learning
- FLOPs: number of FLOating-Point operations [[explanation]](https://openai.com/blog/ai-and-compute/)
  - 1 petaFLOPs = 1e15 FLOPs
