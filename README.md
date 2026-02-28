ClassifEye — Brain Tumor MRI Classifier

A deep learning system that analyzes brain MRI scans and classifies them 
into 4 categories: Glioma, Meningioma, Pituitary Tumor, or No Tumor.

Built with EfficientNetB3 + Transfer Learning. Achieves **89.3% test accuracy**.

## How It Works
- Two-phase training: head training → full fine-tuning
- Grad-CAM heatmaps to visualize which region triggered the diagnosis
- Confidence thresholding — flags results under 70% as Inconclusive

## Run It Yourself (Kaggle — Recommended)
1. Go to [Kaggle Notebooks](https://kaggle.com)
2. Create a new notebook and upload `classifeye.ipynb`
3. Add the dataset: [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)
4. Enable GPU (P100) under Settings → Accelerator
5. Run all cells in order

## Run Locally
```bash
git clone https://github.com/yourusername/classifeye
cd classifeye
pip install -r requirements.txt
jupyter notebook classifeye.ipynb
```
> ⚠️ You'll need to download the dataset from Kaggle and update `DATA_DIR` to your local path.

## Results
| Class       | Precision | Recall | F1  |
|-------------|-----------|--------|-----|
| Glioma      | 0.85      | 0.80   | 0.82|
| Meningioma  | 0.85      | 0.83   | 0.84|
| No Tumor    | 0.91      | 0.99   | 0.95|
| Pituitary   | 0.96      | 0.95   | 0.96|
| **Overall** |           |        |**0.89**|

## Dataset
[Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) 
by Masoud Nickparvar — 7,023 MRI images across 4 classes.

## Disclaimer
This is a research tool intended to assist radiologists. 
It does not replace professional medical diagnosis.
