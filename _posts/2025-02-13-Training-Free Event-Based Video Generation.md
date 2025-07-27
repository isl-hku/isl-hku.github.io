---
layout: post
title: "Controllable Synthesis Using Edge Data and Text Prompts"
description: 
categories: 
header-img: cube.png
lang: en
---



We are excited to announce a new framework called CUBE (Controllable, Unsupervised, Based on Events), developed by researchers at the University of Hong Kong (HKU). This work has been accepted for Oral Presentation at ICIP 2024 and also invited to present at a WACV workshop.

### **Why Event Cameras?**

Event cameras capture only intensity changes at each pixel, making them ideal for high-speed, high dynamic range, and low-power imaging. While this sparse data provides precise edge information, generating photo-realistic or even semantically controllable videos from raw events has been a longstanding challenge—until now.

*Key Idea: Combining Event Edges and Text Prompts*

CUBE bridges event streams and text-guided diffusion models to produce controllable videos without requiring specialized training. First, it extracts the edges from event data. Then, it applies a pre-trained (no extra training needed) diffusion model to translate these edges, guided by user text prompts, into photo-realistic video frames.

1. **Edge Extraction**

Given an event stream $(\varepsilon = \{e _i\})$ with each event $(e _i)$ as $(x_i, y_i, s_i, p_i)$, we form edge maps over \(V\) time segments. The edge map $(\mathbf{I} _j)$ for the $(j)$-th segment is computed by:

$$
\mathbf{I}*j(x,y) = \sum*{i,; e_i \in \varepsilon_j} \frac{|p_i|,\delta(x - x _i),\delta(y - y_i)}{N},
$$

where $(\delta)$ is the Kronecker delta, $(p _i)$ is event polarity $(\pm 1)$, and $(N)$ is the total number of events in that segment. This yields a crisp edge map representing where and when changes occurred.

2. **Diffusion-Based Video Generation**

Using the edge map $(\mathbf{I})$ and a text prompt $(\tau)$, CUBE employs a latent diffusion process. At timestep $(t)$, the denoising can be represented as:

$$
\mathbf{z}_{t \to 0}
\;=\;
\frac{\mathbf{z}_t - \sqrt{1 - \alpha _t} \,\epsilon_{\theta}\bigl(\mathbf{z} _t,\; t,\; \mathbf{I},\; \tau\bigr)}{\sqrt{\alpha _t}},
$$

where $(\mathbf{z} _t)$ is the latent representation at diffusion step $(t)$, and $(\epsilon _{\theta})$ is the denoising model (pre-trained on large text-image datasets)

The reconstructed frames are then interpolated for temporal smoothness, leading to a fully controllable video output—simply specify text prompts (e.g., “a person juggling apples in a Renaissance painting style”) to guide the final appearance and context.

### **Results and Impact**

High-Quality & Consistent Videos: CUBE significantly outperforms existing approaches in terms of visual realism, motion smoothness, and prompt accuracy.

No Large-Scale Training Needed: By building on existing diffusion backbones, the system sidesteps expensive dataset collection and training.

Broad Applicability: Potential uses range from creative video synthesis (film, gaming) to high-speed vision applications (robotics, surveillance), where event cameras thrive.

### **Looking Ahead**

Future directions include fusing texture cues (beyond edges) to enrich details, domain adaptation for real-time scenarios, and further optimization to accelerate event-driven video generation on resource-limited devices.

### **Reference and Code**

**Paper**: “Controllable Unsupervised Event-based Video Generation” – Accepted at [ICIP 2024]

**Code**: GitHub – IndigoPurple/CUBE

If you reference this work, please cite:

```bibtex
@inproceedings{zhao2024controllable,
  title={CONTROLLABLE UNSUPERVISED EVENT-BASED VIDEO GENERATION},
  author={Zhao, Yaping and Zhang, Pei and Wang, Chutian and Lam, Edmund Y.},
  booktitle={2024 IEEE International Conference on Image Processing (ICIP)},
  year={2024}
}
```




Stay tuned for more updates on CUBE, and feel free to explore our open-source repository to try out controllable event-based video generation for yourself!