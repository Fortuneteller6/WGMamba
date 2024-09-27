### 📖 Wavelet Guided State Space Model for Infrared Samll Target Detection

<hr/>

[![](https://img.shields.io/badge/Building-Done-green.svg?style=flat-square)](https://github.com/Fortuneteller6/DFAwareNet) ![](https://img.shields.io/badge/Language-Python-blue.svg?style=flat-square) [![](https://img.shields.io/badge/License-MIT-purple.svg?style=flat-square)](./LICENSE)

> [Paper Link]()  
> Authors: Teng Ma, Kuanhong Cheng, Yubo Wu, Junhuai Li, Haiyan Jin and Huixin Zhou. <br/>
> The code and model weights will be made public after the paper is accepted. Thanks for your attention!

<hr/>

### Datasets Prepare

- IRSTD-1K dataset is available at [IRSTD-1K](https://github.com/RuiZhang97/ISNet).
- NUAA-SIRST dataset is available at [NUAA-SIRST](https://github.com/YimianDai/sirst).
- NUDT-SIRST dataset is available at [NUDT-SIRST](https://github.com/YeRen123455/Infrared-Small-Target-Detection).
- DenseSIRST dataset is available at [DenseSIRST](https://github.com/GrokCV/DenseSIRST).
- We also prepare the txt file for dividing dataset and three datasets, which can be downloaded from [Google Drive]().

<hr/>

### Commands for Taining

- The epoch and bath size for training the [DFAwareNet](https://github.com/Fortuneteller6/DFAwareNet) can be found in the following commands.

```python
python train.py --base_size 256 --crop_size 256 --epochs 500 --dataset IRSTD-1K --split_method 80_20 --model DFAwareNet --deep_supervision True --train_batch_size 4 --test_batch_size 4 --mode TXT
```

```python
python train.py --base_size 256 --crop_size 256 --epochs 1500 --dataset NUAA-SIRST --split_method 80_20 --model DFAwareNet --deep_supervision True --train_batch_size 2 --test_batch_size 2 --mode TXT
```

```python
python train.py --base_size 256 --crop_size 256 --epochs 1500 --dataset NUDT-SIRST --split_method 80_20 --model DFAwareNet --deep_supervision True --train_batch_size 8 --test_batch_size 8 --mode TXT
```

```python
python train.py --base_size 256 --crop_size 256 --epochs 500 --dataset DenseSIRST --split_method 80_20 --model DFAwareNet --deep_supervision True --train_batch_size 8 --test_batch_size 8 --mode TXT
```

### Commands for Testing and Visulization

- For both testing and visulization of different dataset, you just need to change the model weights and the dataset name.

```python
python test.py --base_size 256 --crop_size 256 --st_model IRSTD-1K_DFAwareNet_03_09_2024_18_05_39_wDS --model_dir IRSTD-1K_DFAwareNet_03_09_2024_18_05_39_wDS/mIoU__DFAwareNet_IRSTD-1K_epoch.pth.tar --dataset IRSTD-1K --split_method 80_20 --model DFAwareNet --deep_supervision True --test_batch_size 1 --mode TXT
```

```python
python visulization.py --base_size 256 --crop_size 256 --st_model IRSTD-1K_DFAwareNet_03_09_2024_18_05_39_wDS --model_dir IRSTD-1K_DFAwareNet_03_09_2024_18_05_39_wDS/mIoU__DFAwareNet_IRSTD-1K_epoch.pth.tar --dataset IRSTD-1K --split_method 80_20 --model DFAwareNet --deep_supervision True --test_batch_size 1 --mode TXT
```

<hr/>

### Results and Weights

|  Methods   |    Data    |  Pd   |  Fa   |  IoU  | F1_Score |  Download   |
| :--------: | :--------: | :---: | :---: | :---: | :------: | :---------: |
| DFAwareNet |  IRSTD-1K  | 90.82 | 4.40  | 70.96 |  83.00   | [Weights]() |
| DFAwareNet | NUAA-SIRST | 99.08 | 1.42  | 79.65 |  88.67   | [Weights]() |
| DFAwareNet | NUDT-SIRST | 99.06 | 0.61  | 92.22 |  95.95   | [Weights]() |
| DFAwareNet | DenseSIRST | 90.21 | 10.43 | 69.78 |  82.20   | [Weights]() |

<hr/>

### Acknowledgement

The code of this paper is highly borrowed from [DNANet](https://github.com/YeRen123455/Infrared-Small-Target-Detection). Thanks for their awesome work.

### Citation

If you find the code helpful in your resarch or work, please cite this paper as following.

```

```

### Contact

If you have any questions, please feel free to reach me out at teng_m@yeah.net
