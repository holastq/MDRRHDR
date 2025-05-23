## Multi-Domain Raw-Reversal for Single-Image HDR Reconstruction  
This repository is an official implementation of the paper:

**Multi-Domain Raw-Reversal for Single-Image HDR Reconstruction**

![Head](./img/Head.png)



## Environment Setup

![python](https://img.shields.io/badge/Python-v3.12-green.svg?style=plastic)  ![pytorch](https://img.shields.io/badge/Pytorch-v2.3.0-green.svg?style=plastic)  ![cuda](https://img.shields.io/badge/Cuda-v12.1-green.svg?style=plastic)

* Clone this code

* Create a conda environment and activate it.

  ```
  conda create -n MDRR python=3.12
  conda activate MDRR
  ```

* Install related Pytorch version

  ```
  conda install pytorch==2.3.0 torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
  ```

* Install the required packages

  ```
  cd MDRRHDR
  pip install -r requirements.txt
  ```

  


## Datasets 

- Download the HDR-Real/HDR_Synth datasets from: [GitHub](https://github.com/alex04072000/SingleHDR)

- Download the HDR-Eye datasets from: [EPFL](https://www.epfl.ch/labs/mmspg/downloads/hdr-eye/)

- Download the SI-HDR datasets from: [Apollo](https://www.repository.cam.ac.uk/items/c02ccdde-db20-4acd-8941-7816ef6b7dc7)

- Download the Raise datasets from: [RAISE](http://loki.disi.unitn.it/RAISE/index.php)

  

## Testing Phase

- Download the pre-training model: [Google Drive](https://drive.google.com/file/d/1LfhLFaFoZ-XZnMoqDxXMmugU5ko3-lAX/view?usp=drive_link)

  ```
  mkdir ./checkpoints
  mv MDRR_test.ckpt ./checkpoints
  ```

- Edit the configuration file `./options.py` to the test images file.

- Run the test file:

  ```
  python test.py
  ```

  


## Training Phase

- Edit the configuration file `./options.py` to the test images file. 

- Run the train file:

  ```
  python train.py
  ```

* The training result will be saved in `./training_results/`
* The training checkpoints will be saved in `./training_checkpoints/`



## Metric Method

- Use the `./metric.py` for SSIM and LPIPS:

  ```
  python metric,py -generate your_generate_hdr/ -gt your_gt_hdr/
  ```

- Use the [PU21](https://github.com/gfxdisp/pu21/tree/main) for PSNR,  VSI and [HDR-VDP](https://hdrvdp.sourceforge.net/wiki/) for HDR-VDP-3.



## Results

- In HDR-Eye datasets:

![HDR-Eye](./img/HDR-Eye.png)

- In HDR-Real datasets:

![HDR-Real](./img/HDR-Real.png)

- In HDR-Synth datasets:

![HDR-Synth](./img/HDR-Synth.png)

- In Raise datasets:

![Raise](./img/Raise.png)

- In SI-HDR datasets:

![SI-HDR](./img/SI-HDR.png)
