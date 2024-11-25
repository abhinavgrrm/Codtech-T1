# Codtech-T1
**Name** : Abhinav Gurram  
**Company**: CODTECH IT SOLUTIONS PVT.LTD  
**Intern ID**: CT6WDS2146  
**Domain**: ARTIFICIAL INTELLIGENCE  
**Duration**: OCTOBER 10th, 2024 to NOVEMBER 25th, 2024  
**Mentor**: Santhosh

# CODTECH-Task1
# Task1 - Data Preprocessing

## Steps in Data Preprocessing

### 1. Dataset Loading and Splitting
**Raw Dataset Path**: `/content/drive/MyDrive/Trimmed_AID`

### Action:
The dataset is split into three subsets:
- **70% Training**
- **20% Validation**
- **10% Testing**

The split is performed using the `splitfolders` library and saved at `/content/drive/MyDrive/Trimmed_AID_dataset`.

### 2. Data Augmentation
**Purpose**: To increase dataset diversity and improve model robustness.

### Transformations Applied:
- **Rotation**: Randomly rotate images by up to 20°.
- **Shifts**: Translate images horizontally and vertically by 20%.
- **Shear**: Apply affine transformations.
- **Zoom**: Randomly zoom into images by up to 30%.
- **Horizontal Flip**: Randomly flip images horizontally.

### 3. Data Normalization
**Purpose**: To scale image pixel values into a range of [0, 1] for faster convergence during model training.

### Action: 
Divide pixel values by 255.0.

### 4. Image Inspection
**Purpose**: Analyze and visualize the image dataset to ensure quality and consistency.

### Key Observations:
- All images are of uniform size (600x600 pixels), eliminating the need for resizing.

### Visualization:
- Sample images and their augmentations are displayed to verify transformations.

### 5. Class Distribution Analysis
**Purpose**: To handle class imbalance for unbiased training.

### Action:
- Count the number of images per class.
- Compute class weights using `sklearn`'s `compute_class_weight` to give more importance to underrepresented classes during training.

### 6. Data Generators
**Purpose**: Efficiently load and feed data into the model.

### Setup:
- Use `ImageDataGenerator` to load images in batches of size 32.
- Train and validation datasets use:
  - **Training Augmentation**: Applied for robustness.
  - **Validation Scaling**: No augmentation, only pixel value rescaling.
