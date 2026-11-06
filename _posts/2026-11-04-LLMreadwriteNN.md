
# Sparks of Weight-Space Programming: LLMs can natively read & write neural network weights


**TL;DR**

We find that frontier LLMs are surprisingly good at **natively reading and writing neural network weights**, using a variety of recent tools and algorithms or even via direct weight editing. These results show sparks of Weight-Space Programming, which may extend beyond what we’d expect from humans or conventional algorithms. This might be a big deal for both optimization and interpretability.

Just by looking at the raw weights, GPT-6 Astra **can tell what a network was trained to do**. And without any environment feedback, it **has no trouble writing, from scratch, small game-playing networks** that outplay networks trained with PPO for 100 million steps.

Likewise, asked to make Qwen3.5-0.8B better at math without gradients, Astra **identifies an issue in its weights** causing reasoning loops that Qwen’s own [model card](https://huggingface.co/Qwen/Qwen3.5-0.8B/blob/main/README.md#L856) warns about, and **fixes this by natively editing 0.016% of the weights**. With the same sampling settings, this weight correction raises MATH-500 from 7.9% to 48.1% and generalizes out of the box to instruction following, raising IFEval by 3x.

All of this is possible without allowing Astra to write training loops. It uses its reasoning to figure out what each part of a neural network computes, or should compute, and changes the weights accordingly. We call this **Weight-Space Programming**.

Throughout the history of deep learning, we encoded our simplistic inductive biases into tiny symbolic optimizers like Adam or Muon. This is changing: **our neural network weights will soon be _natively_ optimized by LLMs that deliberately reason about their weights**.


---
# The 'Astra can read and write weights to improve Qwen' post is misleading

### 2026-11-03 · 5 minute read

Stage magicians often do the same trick multiple ways. One iteration uses a gimmick prop, the next one shows you the prop isn’t gimmick but that one palms the object, the third time was a forced choice etc. When you watch the performance you assume there’s only one technique, so each time they do it they seem to debunk your hypothesis about how it must be working.


___

https://rikiyat.github.io/blog/weight-space-programming/
https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/
https://honnibal.dev/blog/astra-read-write-misleading