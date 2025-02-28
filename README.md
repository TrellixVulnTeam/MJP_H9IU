
## Breaking the Chain of Gradient Leakage in Vision Transformers

![Python 3.6](https://img.shields.io/badge/python-3.6.8-green.svg)
![Packagist](https://img.shields.io/badge/Pytorch-1.6.0-red.svg)
![Last Commit](https://img.shields.io/github/last-commit/yhlleo/MJP)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-blue.svg)]((https://github.com/yhlleo/MJP/graphs/commit-activity))
![Contributing](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)


**[[arXiv]](https://arxiv.org/pdf/2205.12551.pdf) | [[Codes]](https://github.com/yhlleo/MJP)** <br> 
Yahui Liu<sup>1</sup>, Bin Ren<sup>1,3</sup>, Yue Song<sup>1</sup>, Wei Bi<sup>2</sup>, Nicu Sebe<sup>1</sup> and Wei Wang<sup>1</sup> <br>
<sup>1</sup>University of Trento, Italy, <sup>2</sup>Tencent AI Lab, China,
<sup>3</sup>University of Pisa, Italy<br>

<p align="center">
<img src="figures/gradient-attack.jpg" width="800px"/>
<br>
Visual comparisons on image recovery with gradient attacks.
</p>

### Datasets

|Dataset|Download Link|
|:-----|:-----|
|[ImageNet](https://www.image-net.org/)|[train](http://www.image-net.org/data/ILSVRC/2012/ILSVRC2012_img_train.tar),[val](http://www.image-net.org/data/ILSVRC/2012/ILSVRC2012_img_val.tar)|


 - Download the datasets by using codes in the `scripts` folder.

```
dataset_name
  |__train
  |    |__category1
  |    |    |__xxx.jpg
  |    |    |__...
  |    |__category2
  |    |    |__xxx.jpg
  |    |    |__...
  |    |__...
  |__val
       |__category1
       |    |__xxx.jpg
       |    |__...
       |__category2
       |    |__xxx.jpg
       |    |__...
       |__...
```

### Checkpoints 
You can find our pretrained checkpoints and 999 images sampled from ImageNet for attacking [here](https://drive.google.com/drive/folders/1P6LnqhLTyG7CRcb7_NsFDVmQ1cOFoNeV?usp=sharing).

### Training 

After prepare the datasets, we can simply start the training with 8 NVIDIA V100 GPUs:

```
$ sh train.sh
```

### Evaluation 

 - Accuracy on Masked Jigsaw Puzzle

```
$ python3 eval.py 
```

 - Consistency on Masked Jigsaw Puzzle

```
$ python3 consistency.py
```

 - Evaluations on image reconstructions

See the codes [`MSE`](./eval/cal_mse.py), [`PSNR/SSIM`](./eval/cal_psnr_ssim.py), [`FFT2D`](./eval/cal_fft2d.py), [`LPIPS`](cal_lpips.py).

### Gradient Attack

We refer to the public repo: [JonasGeiping/breaching](https://github.com/JonasGeiping/breaching).

### Acknowledgement

This repo is built on several existing projects:

 - [Swin-Transformer](https://github.com/microsoft/Swin-Transformer)
 - [BeiT](https://github.com/microsoft/unilm/tree/master/beit)
 - [VTs-Drloc](https://github.com/yhlleo/VTs-Drloc)

### Citation

If you take use of our code, please cite our papers:

```
@article{liu2022breaking,
    author    = {Liu, Yahui and Ren, Bin and Song, Yue and Bi, Wei and Sebe, Nicu and Wang, Wei},
    title     = {Breaking the Chain of Gradient Leakage in Vision Transformers},
    journal    = {arXiv:2205.12551},
    year      = {2022}
}
```

If you have any questions, please contact me without hesitation (yahui.liu AT unitn.it).

