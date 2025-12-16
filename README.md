# Less is Better: Sparse Instance Learning for Few-Shot Object Detection

> [[Paper](xxxxxxxxx)] <br>
> Yali Huang, Jie Mei, Ziyi Wu, Yiming Yang, Hongru Zhao, Mingyuan Jiu*, Hichem Sahbi <br>
> School of Computer and Artificial Intelligence, Zhengzhou University, China<br>
> Engineering Research Center of Intelligent Swarm Systems, Ministry of Education, China<br>National SuperComputing Center in Zhengzhou, Zhengzhou, China<br>Dongfeng Commercial Vehicle Co.,Ltd, China<br>Sorbonne University, CNRS, LIP6, F-75005, Paris, France
>

---
## 🧠Overview
**In this Paper**, We:
1) We introduce a **dual sparsity mechanism** that applies instance feature sparsification not only to few-shot support images but also to query images. This enables the model to retain salient foreground semantics while effectively filtering out redundant and noisy
features, thereby alleviating overfitting and enhancing robustness in low-data scenarios.
2) We develop a dynamic prototype calibration strategy to refine class prototypes using query instances during adaptation. This accelerates prototype alignment to the target domain and significantly improves detection accuracy under few-shot constraints.
3) Extensive experiments conducted on multiple CD-FSOD benchmarks demonstrate that SI-ViTO significantly
outperforms state-of-the-art methods, confirming that leveraging sparse and discriminative representations, rather than
abundant redundant features, lead to superior performance in cross-domain few-shot detection.

**In this repo**, we provide: 
1) links and splits for target datasets;
2) codes for our SI-ViTO method.
---
## 🧠Method
![SI-ViTO](Doc/SI-ViTO-pipeline.png)
## 🛠️ Environment Setup

An anaconda environment is suggested, take the name "cdfsod" as an example:

```
git clone git@github.com:hyali/SI-ViTO.git
conda create -n cdfsod python=3.9
conda activate cdfsod
pip install -r SI-ViTO-main/requirements.txt 
pip install -e ./SI-ViTO-main
cd SI-ViTO-main
```

## 📂 Dataset Preparation

The target datasets could be easily downloaded in the following links: (If you use the datasets, please cite them properly, thanks.)
- [Dataset Link from Google Drive](https://drive.google.com/drive/folders/16SDv_V7RDjTKDk8uodL2ubyubYTMdd5q?usp=drive_link)
- [Dataset Link from 百度云盘](https://pan.baidu.com/s/1MpTwmJQF6GtmnxauVUPNAw?pwd=ni5j)

To train SI-ViTO on a custom dataset, please refer to DATASETS.md for detailed instructions.

## 🏋️ Training

To train the model: 

1. download weights: download pretrained model from [DE-ViT](https://github.com/mlzxy/devit/blob/main/Downloads.md).
2. download the CD-FSOD benchmark. Put them in ./SI-ViTO-main/datasets/
3. run script:

```
bash main_results.sh
```

pretrained model: [Google Drive](https://drive.google.com/file/d/1KfNnkM7SewMN6nroRSG-GNiuaEELx6EP/view?usp=drive_link)


## Acknowledgement

Our work is built upon [CD-ViTO](https://github.com/lovelyqian/CDFSOD-benchmark), and also we use the codes of [ViTDeT](https://github.com/ViTAE-Transformer/ViTDet), [Detic](https://github.com/facebookresearch/Detic) to test them under this new benchmark. Thanks for their work.
## 🔍 Inference & Evaluation

Run inference:

#### Evaluation

![compareResult](Doc/compare.png)

![InferenceResult](Doc/visualization.png)


## 📄 Citation

If you use our method or codes in your research, please cite:

```
@inproceedings{SI-ViTO,
  title={Less is Better: Sparse Instance Learning for Cross-Domain Few-Shot Object Detection},
  author={Huang, Yali and Mei, Jie and Wu Ziyi, and Yang, Yiming and Zhao Hongru, and Jiu, Mingyuan and Hichem Sahbi},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence. 2026.}
}
```





