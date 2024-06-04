# Unconditional Diffusion Model for Image Generation

This repository contains an implementation of an unconditional diffusion model for generating images of deers and trucks using UNET2D and the DDPMScheduler.

## Key Features and Capabilities
- Utilizes UNET2D architecture for image generation.
- Implements the DDPMScheduler for improved training stability.

## Implementation Details
- **Programming Language/Framework:** Python with Google Colab
- **Dependencies:** Refer to `requirements.txt` for required packages.

## Installation and Setup
- Save the code folder in `/content/drive/MyDrive/{repository_name}/`
- Open `Diffusion Models - Image Generation.ipynb`
- Mount your Google Drive.
- Install dependencies by running:
```bash
!pip install -r requirements.txt
```   
## Run the training script:
```bash 
!python train.py
```
## Dataset
`CIFAR-10` dataset is used for training, loaded in the `data.py` file.
## Input and Output Formats
Input: Images from CIFAR-10 dataset

Output: Generated images of deers and trucks
## Running the Model
Execute `train.py` to start the training loop.
You will then be prompted to log into your wandb account using your api key.
The training loop generates samples at regular intervals and saves them to WandB.
## Training from Checkpoint
In section 2 of `Diffusion Models - Image Generation.ipynb` specify the path to your desired checkpoint (that was previously saved in wandb) as the value for `artifact_name`and run the cell. 

The model will be saved in local storage under `/content/artifacts/model_epoch_{checkpoint_epoch_value}:{version}/model_checkpoint.pt`

After, proceede to run `!python train.py` with the checkpoint path as the parameter. 
```bash
!python train.py --checkpoint_path "{checkpoint_path}"
```
The training loop will then commence from the specified checkpoint.

## Customizable Parameters
- Model Saving: Model is saved every 10 epochs. Modify the `save_model_every` parameter in train.py to change the frequency.
- Original File Saving: Original images from CIFAR-10 are saved as WandB artifacts. Comment out line 66 in `data.py` to disable this feature if necessary.
## Performance Metrics
FID score and loss metrics are logged to WandB for performance evaluation.
## WandB
- Wandb is initialised in `train.py`
- The `project`, `entity` and `name` can be modified from the `train.py` file.
# Diffusion-Model
