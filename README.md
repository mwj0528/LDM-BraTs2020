# LDM-BraTs2020
Using LDM to perform Generation task using multiple modality data of 2D slice of BraTs2020

## Reference
### [latent-diffusion](https://github.com/CompVis/latent-diffusion.git)

## Installation
Implementation is conducted on Python 3.10. To install the environment, please run the following.
```
conda env create -f environment.yaml
conda activate ldm
```
## Run

I use a 6 NVIDIA TITAN RTX GPU for our experiments.
I used an autoencoder trained using the VQGAN code in the repo below.
### [VQ-GAN](https://github.com/mwj0528/VQGAN_BraTs2020.git)

### Train
```
python main.py --base configs/latent-diffusion/brats-ldm-vq.yaml -t --gpus 0,1,2,3,4,5 (to use 6 GPUs.)
```
### Sample
```
python scripts/sample_diffusion.py -r models/ldm/brats/last.ckpt -l models/ldm/brats/ -n 5 --batch_size 1 -c 200
```

## Example Result

![sample_000000](https://github.com/user-attachments/assets/4ec6eadb-2409-4993-89d4-1de3a8fd4eea)
![sample_000004](https://github.com/user-attachments/assets/177d7797-9884-4b54-9114-06aef7b254e1)
![sample_000007](https://github.com/user-attachments/assets/064b2907-0992-40ee-822c-cc4c2f4843e6)

