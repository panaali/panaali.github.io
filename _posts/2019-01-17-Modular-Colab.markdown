---
layout: post
title: Why you shouldn't try writing modular notebooks in Google Colab
date: '2019-01-17 12:43:53 -0500'
categories: coding
published: true
---
Recently, I started using Google Colab and wanted to create nice modular notebooks. I found [ipynb](https://github.com/ipython/ipynb "ipynb") a library to import a notebook in another notebook. The first issue was that the ipynb was not accepting Google Colab notebooks as a valid jupter notebook. I [fixed](https://github.com/panaali/ipynb) that issue but it was not enough. The next problem was that the if I changed the code of other notebooks I had to restart my kernel to reload the imported notebook. I tried both `importlib.reload` and `%autoreload`. It seems that they should solve the problem but unfortnatly it took ~20 seconds for Google Colab to get load the new saved notebook. This delay was not acceptable for my work since I'm developing my notebooks and there are a lot of changes every few seconds that I want to test and get the result, hence I decided to put aside the idea of writing modular code in Google Colab. Besides this, the [ipynb](https://github.com/ipython/ipynb "ipynb") has [can not deal](https://github.com/ipython/ipynb/issues/6) with magic functions like `%ls` or bash functions `!pip` and the `ipynb` development seems not an active.

Want to know more about why notebooks are not good (yet)? Watch this video: [!["I don't like notebooks" by Joel Grus](http://i3.ytimg.com/vi/7jiPeIFXb6U/hqdefault.jpg)](https://www.youtube.com/watch?v=7jiPeIFXb6U)
[Slides](https://docs.google.com/presentation/d/1n2RlMdmv1p25Xy5thJUhkKGvjtV-dkAIsUXP-AL4ffI/edit)
