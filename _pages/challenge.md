---
layout: schedule
order: 4
permalink: /challenge
title: Challenge
# redirect_from: /index.html
desc_title: SyntaGen Competition
# description: <strong>The Good, the Bad and the Ugly</strong> - Modern AI development requires using and sharing of models and data safely. Uncovering backdoor, a foe and a friend at the front door.
social: true
---

### Dataset and metric
The primary objective of this competition is to drive innovation in the creation
of high-quality synthetic datasets, leveraging only the pretrained [Stable Diffusion](https://huggingface.co/spaces/stabilityai/stable-diffusion) 
and the 20 class names from [PASCAL VOC 2012](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/) for semantic segmentation. The evaluation of synthetic dataset quality involves training a [DeepLabv3](https://arxiv.org/abs/1706.05587) model on the synthetic dataset and subsequently assessing its performance on a private test set on the task of semantic segmentation. Submissions are ranked based on the **mIoU** metric. This competition framework mirrors the practical
application of synthetic datasets, particularly in scenarios where they replace real datasets.

### Requirements
Teams are required to upload their synthetic datasets to **Google Drive** for public access. The dataset should include a maximum of **10K** pairs of synthesized images and semantic segmentations, each image being **512x512** in size. We will supply a Google Colab codebase for exemplifying some random training images and their annotations, DeepLabv3 training and evaluation, using a **Resnet-50** backbone, and showing qualitative results. Training and evaluation time for DeepLabv3 is capped at **100K iterations** with a **batch size of 8**.  The codebase should remain unchanged except for the Google Drive file ID provided by each team. For text prompts, participants can leverage various methods, including LLMs like [ChatGPT](https://chat.openai.com/). For text-to-image generation, participants can choose either **Stable Diffusion (v1.x) or (v2.x)**. However, participants can freely modify Stable Diffusion without changing its pretrained weights and using additional segmentation datasets.

### Submission and evaluation
The submission comprises two phases with two separate deadlines,
outlined as follows:

1.  **Random seed + DeepLabv3 + Dataset**. By the first deadline in this phase, each
team must use their method to generate their synthetic dataset and train a DeepLabv3 on
it. Each team must submit:
* The **random seed** used in their model for dataset generation, 
* The **generated dataset** 
* The **checksum of the trained DeepLabv3**. The checksum
code will be provided as part of the Colab codebase. Modifications to the model, the trained
DeepLabv3, or the generated dataset are prohibited after this deadline.

2.  **Code + Score**. After the first deadline, our private test set will be released to each team.
Each team must evaluate their trained DeepLabv3 on the test set and submit their code and
mIoU score on the same Colab file as in the previous deadline by the final deadline.

Entries will be evaluated based on their mIoU, and the top submissions will be contacted for further
verification. These selected participants will be required to share their code (via **GitHub**) to replicate
the synthetic datasets (consisting of images and annotations) using the specified random seed and
checksum. Additionally, the provided Google Colab file will be employed to reproduce both the
training and inference processes of DeepLabv3, ensuring accurate results and confirming adherence
to Stable Diffusion as the exclusive text-to-image generator. Any submissions found to
be non-compliant or in violation of the rules will be disqualified. In such instances, the evaluation
process will continue with the subsequent submissions until the final top 2 are determined

### Prizes and presentation: 
We will award the top 2 teams with cash prizes and invite them to write a report and present their work at the workshop (10 minutes each).

<!-- ### Ethical considerations for the datasets
Since the evaluated dataset is the validation set of PASCAL VOC 2012, it shares the same ethical considerations with PASCAL VOC 2012. Besides, the generated
synthetic training set has new considers including

 * **Data Bias and Fairness**: The creation of synthetic datasets through Stable Diffusion
can introduce unintended biases, potentially deviating from real-world data characteristics.
Ethical vigilance is essential to identify and rectify any biases, ensuring that the synthetic
datasets remain representative, unbiased, and fair.

* **Privacy and Consent**: Although synthetic datasets do not involve real individuals’ data,
traces of underlying characteristics might inadvertently capture sensitive information. Up-holding ethical principles necessitates the thorough anonymization or removal of such data
traces to protect privacy and respect consent standards. -->

### Important Dates

* **Competition announcement**: Feb 22nd, 2024
* **Submission start**: Mar 1st, 2024
* **Submission deadline 1 for random seed, DeepLabv3, and dataset**: May 24th, 2024
* **Submission deadline 2 for Colab code and mIoU score**: May 27th, 2024
* **Award announcemen**: Jun 7th, 2024
* **Report and code upload for winners**: Jun 14th, 2024

### Discussion
* TBD