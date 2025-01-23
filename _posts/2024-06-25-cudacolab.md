---
title: cudf_pandas_stocks_demo
tags:
  - aktien
  - pandas
  - Python
  - stock
  - gpu
date: 2024-06-25
toc: true
toc_sticky: true
---

# cudf_pandas_stocks_demo

uDF is a Python GPU DataFrame library (built on the Apache Arrow columnar memory format) for loading, joining, aggregating, filtering, and otherwise manipulating tabular data using a DataFrame style API in the style of pandas.

cuDF includes a pandas accelerator mode (`cudf.pandas`), enabling you to accelerate your pandas workflows without requiring any code change.

This notebook highlights the impact of GPU-acceleration for common operations and analytical questions analyzing a real-world dataset of stock prices.

For a deeper introduction and insight into how things work under the hood, we encourage you to run the [10 Minutes to RAPIDS cuDF's pandas accelerator mode Colab notebook](https://www.google.com/url?q=https%3A%2F%2Fnvda.ws%2Frapids-cudf) or visit [https://rapids.ai/cudf-pandas/](https://www.google.com/url?q=https%3A%2F%2Frapids.ai%2Fcudf-pandas%2F).

The data we'll be working with is a subset of the [USA 514 Stocks Prices NASDAQ NYSE dataset](https://www.google.com/url?q=https%3A%2F%2Fwww.kaggle.com%2Fdatasets%2Folegshpagin%2Fusa-stocks-prices-ohlcv) from Kaggle.

We'll start by downloading the dataset from NVIDIA's Public Google Cloud Storage bucket to provide faster download speeds to Colab. This should take under 30 seconds.


https://colab.research.google.com/github/rapidsai-community/showcase/blob/main/getting_started_tutorials/cudf_pandas_stocks_demo.ipynb#scrollTo=WmOguzNUcw4F