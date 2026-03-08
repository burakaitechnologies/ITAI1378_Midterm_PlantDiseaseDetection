# Dataset Information

## PlantVillage Dataset

- **Source:** https://github.com/spMohanty/PlantVillage-Dataset
- **Alternative:** Available on [Kaggle](https://www.kaggle.com/datasets/emmarex/plantdisease)
- **Size:** ~54,000 images
- **Classes:** 38 (healthy + diseased leaves across 14 plant species)
- **Format:** JPEG images, organized in folders by class name
- **License:** Open-source (MIT)

## Download Instructions

### Option 1: Kaggle (Recommended)
```bash
# Install kaggle CLI
pip install kaggle

# Download dataset
kaggle datasets download -d emmarex/plantdisease
unzip plantdisease.zip -d plantvillage/
```

### Option 2: Direct Clone
```bash
git clone https://github.com/spMohanty/PlantVillage-Dataset.git
```

## Class Examples

| Plant | Disease | Samples |
|-------|---------|---------|
| Tomato | Early Blight | ~1,000 |
| Tomato | Late Blight | ~1,909 |
| Tomato | Healthy | ~1,591 |
| Potato | Early Blight | ~1,000 |
| Potato | Late Blight | ~1,000 |
| Potato | Healthy | ~152 |
| Apple | Apple Scab | ~630 |
| Apple | Healthy | ~1,645 |

## Data Split

| Split | Percentage | Purpose |
|-------|-----------|---------|
| Train | 70% | Model training |
| Validation | 15% | Hyperparameter tuning |
| Test | 15% | Final evaluation |

## Note

The actual image data is NOT included in this repository due to size. Follow the download instructions above to obtain the dataset.
