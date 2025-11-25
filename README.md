# Hand Gesture Recognition for Multimodal Perception and Embodied Intelligence Systems

**Choose Language:**
- [English](README.md) • [Chinese (Simplified)](README.zh-CN.md)
## Project Overview

This project implements a robust hand gesture recognition subsystem designed for hospital non-medical needs support within a broader multimodal perception and embodied intelligence framework. The module enables intuitive, touch-free human-computer interaction through real-time visual gesture interpretation.

## Dataset Access

**Important**: Due to GitHub file size limitations, the complete dataset is hosted on Google Drive:

📁 **Dataset Download**: [Google Drive Link](https://drive.google.com/drive/folders/1I_ua6nDwShRZlqOnakeSHIVZKav0ZFX5?usp=drive_link)

### Required Files:
- `train/` - Training images folder
- `val/` - Validation images folder  
- `test/` - Test images folder
- `train_labels.csv` - Training set labels
- `val_labels.csv` - Validation set labels
- `test_labels.csv` - Test set labels
- `dataset_config.yaml` - Dataset configuration file

### Setup Instructions:
1. Download all files from the Google Drive link above
2. Place them in your project directory under `hagrid_classification/`
3. Ensure the directory structure matches:

```
hagrid_classification/
├── dataset_config.yaml
├── train_labels.csv
├── val_labels.csv
├── test_labels.csv
├── train/
├── val/
└── test/
```


## Dataset Details

- **Source**: HaGRID public dataset
- **Total Samples**: 231,177 images
- **Classes**: 9 hand gestures
- **Train/Val Split**: 204,187 (88.3%) / 26,990 (11.7%)
- **Class Balance**: 0.86:1 max/min ratio

### Gesture-Function Mapping
| Gesture | Function | Use Case |
|---------|----------|----------|
| rock | Wake system | System interaction |
| call | Call nurse | Emergency services |
| one | Raise bed | Bed adjustment |
| fist | Lower bed | Bed adjustment |
| three | TV on/off | Entertainment control |
| two_up | Channel up | Entertainment control |
| palm | Lights on/off | Environment control |
| ok | Confirm action | System interaction |
| like | End interaction | System interaction |

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Swin Transformer | 0.9919 | 0.9919 | 0.9919 | 0.9919 |
| MobileNetV2 | 0.9855 | 0.9855 | 0.9855 | 0.9855 |
| Vision Transformer | 0.9773 | 0.9774 | 0.9773 | 0.9773 |
| ResNet18 | 0.9758 | 0.9758 | 0.9758 | 0.9758 |

## Quick Start

### Environment Setup
```bash
conda create -n gesture_recognition python=3.8
conda activate gesture_recognition
pip install torch torchvision transformers timm pandas numpy matplotlib seaborn scikit-learn tqdm jupyter opencv-python
```
### Training
```python
# Run training notebooks from model code/
jupyter notebook "model code/ResNet18.ipynb"
```

### Project Structure
```text
hagrid_classification/
├── dataset_config.yaml          # Dataset configuration
├── train_labels.csv             # Training labels
├── val_labels.csv               # Validation labels
├── test_labels.csv              # Test labels
├── train/                       # Training images
├── val/                         # Validation images
├── test/                        # Test images
└── model code/                  # Training code & models
    └── *.ipynb                  # Training notebooks
```
### Citation
If using this project, please cite the HaGRID dataset and our paper.
### License
Academic use only. Commercial use requires permission.

```text
Note: This gesture recognition module is part of a larger multimodal perception and embodied intelligence system for hospital environments.
