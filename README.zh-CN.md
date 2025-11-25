# 多模态感知与具身智能系统的手势识别模块

**Choose Language:**
- [英语](README.md) • [中文 (简体)](README.zh-CN.md)

## 项目概述

本项目实现了一个具有鲁棒性的手势识别子系统，专为医院非医疗需求支持设计，是更大规模多模态感知与具身智能框架的一部分。该模块通过实时视觉手势解析，支持直观、无接触的人机交互。

## 数据集获取

**重要提示**: 由于 GitHub 文件大小限制，完整数据集托管在 Google Drive:

📁 **数据集下载**: [Google Drive 链接](https://drive.google.com/drive/folders/1I_ua6nDwShRZlqOnakeSHIVZKav0ZFX5?usp=drive_link)

### 必需文件:
- `train/` - Training images folder
- `val/` - Validation images folder  
- `test/` - Test images folder
- `train_labels.csv` - Training set labels
- `val_labels.csv` - Validation set labels
- `test_labels.csv` - Test set labels
- `dataset_config.yaml` - Dataset configuration file

### 配置步骤:
1. 从上述 Google Drive 链接下载所有文件
2. 将文件放置在项目目录的 hagrid_classification/ 文件夹下 
3. 确保目录结构如下:

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


## 数据集详情

- **来源**: HaGRID 公开数据集
- **样本总数**: 231,177 张图像
- **类别数量**: 9 种手势
- **训练 / 验证集划分**: 204,187 张（88.3%）/ 26,990 张（11.7%）
- **类别平衡**: 最大 / 最小样本比为 0.86:1

### 手势 - 功能映射表
| 手势（Gesture） | 功能（Function） | 应用场景（Use Case） |
|-----------------|------------------|----------------------|
| 摇滚（rock）    | 唤醒系统         | 系统交互             |
| 打电话（call）    | 呼叫护士         | 紧急服务             |
| 举食指（one）    | 升高病床         | 病床调节             |
| 拳头（fist）    | 降低病床         | 病床调节             |
| 数字3（three）  | 电视开关         | 娱乐控制             |
| 双指上举（two_up） | 频道上调       | 娱乐控制             |
| 手掌（palm）    | 灯光开关         | 环境控制             |
| OK手势（ok）    | 确认操作         | 系统交互             |
| 赞（like）    | 结束交互         | 系统交互             |

## Model Performance

| 模型               | 准确率（Accuracy） | 精确率（Precision） | 召回率（Recall） | F1分数（F1-Score） |
|--------------------|--------------------|---------------------|------------------|--------------------|
| Swin Transformer   | 0.9919             | 0.9919              | 0.9919           | 0.9919             |
| MobileNetV2        | 0.9855             | 0.9855              | 0.9855           | 0.9855             |
| Vision Transformer | 0.9773             | 0.9774              | 0.9773           | 0.9773             |
| ResNet18           | 0.9758             | 0.9758              | 0.9758           | 0.9758             |

## 快速开始

### 环境配置
```bash
conda create -n gesture_recognition python=3.8
conda activate gesture_recognition
pip install torch torchvision transformers timm pandas numpy matplotlib seaborn scikit-learn tqdm jupyter opencv-python
```
### 模型训练
```python
# Run training notebooks from model code/
jupyter notebook "model code/ResNet18.ipynb"
```

### 项目结构
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
### 引用说明
如果使用本项目，请引用 HaGRID 数据集及我们即将发表的相关论文。
### 许可证
仅限学术使用。商业使用需获得授权。

```text
注：该手势识别模块是面向医院环境的多模态感知与具身智能系统的一部分。
