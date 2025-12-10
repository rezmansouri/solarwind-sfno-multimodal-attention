# A Further Step Toward Machine Learning Surrogates of the Solar Wind

## CSC8851 - Deep Learning - Dr. Venkateswara

This repository contains code for training and evaluating a multi-modal Spherical Fourier Neural Operator (SFNO) surrogate for solar wind prediction, modeling radial velocity and electrical current density.

## Model architecture

<img src="images/model.jpg">

## CR2284 - Without attention

<img src="images/exp50-cr2284.gif">

## CR2284 - With attention

<img src="images/exp52-cr2284.gif">

## Installation

1. Clone the repository:

```bash
git clone <repo_url>
cd <repo_name>
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

## Training

Models can be trained using the train.py script with the following command-line arguments:

```bash
python src/train.py <data_path> <batch_size> <n_epochs> <encoder_hidden_channels> <hidden_channels> <n_layers> <scale_up> <loss_fn_str> <attention>
```

- `data_path`: Path to the dataset
- `batch_size`: Batch size for training (integer)
- `n_epochs`: Number of training epochs (integer)
- `encoder_hidden_channels`: Hidden channels in the encoder (integer)
- `hidden_channels`: Hidden channels in the SFNO trunk (integer)
- `n_layers`: Number of SFNO blocks (integer)
- `scale_up`: Upscaling factor (integer)
- `loss_fn_str`: Loss function to use (string, e.g., "MSE")
- `attention`: Whether to use attention (1 for yes, 0 for no)

## Example:

```bash
python src/train.py ./data 16 100 64 64 4 2 MSE 1
```