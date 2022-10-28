# ArcGAN: “Generative Adversarial Networks for 3D Architectural Image Generation”

**Figure:** *Recovered 3D shape and rotation&relighting effects using ArcGAN.*

> **ArcGAN: “Generative Adversarial Networks for 3D Architectural Image Generation”** <br>
> Drashty Ranpara, Raghul V, Arun Mozhi Devan, Samiksha Shukla <br>

In this repository, we present **ArcGAN**, which reconstructs the 3D shape of an image using 2D image GANs in an unsupervised manner.
Our method **does not rely on mannual annotations or external 3D models**, yet it achieves high-quality 3D reconstruction, object rotation, and relighting effects.

## Requirements

* python>=3.6
* [pytorch](https://pytorch.org/)=1.1 or 1.2
* [neural_renderer](https://github.com/daniilidis-group/neural_renderer)
    ```sh
    pip install neural_renderer_pytorch  # or follow the guidance at https://github.com/elliottwu/unsup3d
    ```
* [mmcv](https://github.com/open-mmlab/mmcv)
    ```sh
    pip install mmcv
    ```
* other dependencies
    ```sh
    conda install -c conda-forge scikit-image matplotlib opencv pyyaml tensorboardX
    ```

## Dataset and pre-trained weights

To download dataset and pre-trained weights, simply run:
```sh
sh scripts/download.sh
```

## Training
https://github.com/DrashtySoni/ArcGAN
```

**Example1**: training on car images:
```sh
sh scripts/run_car.sh
```
This would run on 4 GPUs by default. You can view the results at `results/car/images` or Tensorboard.

**Example2**: training on lsun church images:
```sh
!python run.py --launcher none --config configs/church.yml 2>&1 | tee results/architecture/log.txt
```

**Note**:  
\- For church, the quality of StyleGAN2 samples vary a lot, thus our approach may not produce good result on every sample. The downloaded dataset contains examples of good samples.

## Acknowledgement

Some part of the code is borrowed from [Unsup3d](https://github.com/elliottwu/unsup3d) and [StyleGAN2](https://github.com/rosinality/stylegan2-pytorch).
`
