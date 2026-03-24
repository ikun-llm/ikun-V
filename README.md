<p align="center"><img src="https://raw.githubusercontent.com/ikun-llm/.github/main/profile/logo.png" width="120" /></p>
<h2 align="center">ikun-V</h2>
<p align="center"><b>能看懂篮球的模型</b><br/><sub>Level 3 | 进阶篇</sub></p>

---

> 终于能看懂篮球视频了！铁山靠的视觉识别准确率：100%

## 你将学到

- 视觉语言模型 (VLM) 架构原理
- Vision Encoder（图像编码器）如何提取视觉特征
- Projector（投影层）如何连接视觉和语言
- 多模态训练数据格式
- 从纯文本模型扩展为多模态模型的方法

## 参考项目

基于 [MiniMind-V](https://github.com/jingyaogong/minimind-v) — MiniMind 的多模态扩展

## VLM 架构

```
图片 🖼️
  ↓
Vision Encoder (CLIP/SigLIP)
  ↓ 视觉特征
Projector (线性投影)
  ↓ 映射到语言空间
┌─────────────────────┐
│   LLM (ikun-2.5B)   │ ← 同时接收文本和视觉 token
│  "这张图里有篮球！"  │
└─────────────────────┘
```

## 多模态的关键挑战

| 挑战 | 解决方案 |
|------|---------|
| 视觉和语言在不同空间 | Projector 做空间映射 |
| 图片太大 token 太多 | 下采样/池化减少视觉 token |
| 训练数据不够 | 分阶段：先对齐再指令微调 |
| 幻觉问题 | 高质量数据 + RLHF 对齐 |

## 系列导航

| Level | Repo | 学什么 |
|-------|------|--------|
| 1 | [ikun-tokenizer](https://github.com/ikun-llm/ikun-tokenizer) | 分词器原理 |
| 1 | [ikun-pretrain](https://github.com/ikun-llm/ikun-pretrain) | 从零预训练 |
| 1 | [ikun-2.5B](https://github.com/ikun-llm/ikun-2.5B) | SFT + LoRA 微调 |
| 2 | [ikun-DPO](https://github.com/ikun-llm/ikun-DPO) | 偏好对齐 |
| 2 | [ikun-GRPO](https://github.com/ikun-llm/ikun-GRPO) | 强化学习 |
| 2 | [ikun-Reason](https://github.com/ikun-llm/ikun-Reason) | 推理模型 |
| 3 | [ikun-MoE](https://github.com/ikun-llm/ikun-MoE) | 混合专家 |
| 3 | [ikun-Distill](https://github.com/ikun-llm/ikun-Distill) | 知识蒸馏 |
| **3** | **ikun-V** ← 你在这里 | **多模态** |
| 4 | [ikun-deploy](https://github.com/ikun-llm/ikun-deploy) | 部署 |
