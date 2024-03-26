---
layout: post
title: Intro2-Computational-Neuronscience-w1
date: 2019-05-11 16:20:40
categories:
- Computational Neuroscience
tags:
- Computational Neuroscience
thumbnail: /assets/img/Intro2-Computer-Neuroscience-w1/001.png
---

[TOC]





## 1. 使用Python作科学计算(scientific python)



* 在scripts前习惯添加如下代码 :

```python
from __future__ import division
import numpy as np
import matplotlib.pyplot as plt
```

* 使用 pickle module 读取数据：

```python
import pickle

data = {'stim': np.array([1,2,3]), 'response': np.array([4,5,6])}

with open('my_data.pickle','wb') as f:
    pickle.dump(data,f)
    
with open('my_data.pickle','rb') as f:
	new_data = pickle.load(f)
```



## 2. Models used in CN

### Models



* Desciptive Models—— what nervous system do
* Mechanistic Models——how they function
* Interpretive Models——why they operate in particular ways



### Receptive Fields.Experiment



Example to explain: ——Receptive Fields

​	Hubel and Wiesel, c. 1965	

<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/001.png" class="img-fluid z-depth-1" zoomable=true %}
</div>


​		showed that the cat's cell responded robustly when the bar of light oriented at 45° 

​	感受野，感受器受刺激兴奋时，通过感受器官中的向心神经元将神经冲动（各种感觉信息）传到上位中枢，一个神经元所反应（支配）的刺激区域就叫做神经元的感受野（receptive field）【受纳野】。



<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/002.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

### Receptive Fields.Models

* Desription

  1. Retina 视网膜

  layer of tissue back of your eyes(retinal ganglion cells[视网膜神经节细胞] there)

  2. Lateral Geniculate Nucleus(LGN)[外侧膝状体]

  3. the Primary Visual Cortex(V1)[初级视皮层]

     意即通过实验发现视网膜和V1处的细胞有不同的感受野，这是一种**科学发现**,发现其**形式因**

     

     
     
<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/004.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/005.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

* Machanical

<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/006.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

  解剖学(anatomy)发现众多的LGN细胞连接到独立的V1细胞，Hubel&Wiesel则推测V1 cell感受野的变形是由于不同LGN细胞的前馈输入叠加。(feed-forward input)

<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/008.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

  这种模型提供了一种**科学解释**，解释其**动力因**

  

* Interpretive Model

为什么V1细胞要长成这个样子？这种interpretive model解释了其**目的因**

进化论的角度：为了表达客观世界图象更加的真实、更加有效

（represent images as faithfully and as efficiently as possible)

<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/009.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

验证模型的正确性：

建模：

	* 输入：自然图象
	* I^ = (自己构造的RFi)*wi
	* 将I^ 与输入的 I 对比，比较二者灰度值的差异
	* 找到最有效率、最优的RFi



<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Intro2-Computer-Neuroscience-w1/010.png" class="img-fluid z-depth-1" zoomable=true %}
</div>



## 3. Conclusion



亚里士多德针对认识论提出了“四因说”：每个对象都有其“形式因”，“质料因”，“动力因”，“目的因”

CN的三个模型，DESP研究形式因和质料因，MACHA研究动力因，INTERP研究目的因.

重要的还是对自己的模型进行验证:)