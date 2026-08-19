# Brain Tumor Prediction

A deep learning notebook for classifying brain tumors from MRI images using transfer learning on VGG16.

## Current Status

This repo currently contains the **training notebook only**. The Flask web app, trained model file, and datasets referenced in earlier drafts of this README are not yet included — see [Roadmap](#roadmap) below.

## Dataset

Trained on a 4-class brain MRI dataset (`glioma`, `meningioma`, `notumor`, `pituitary`), split into `Training` (5,712 images) and `Testing` (1,311 images) folders. The filename convention (`Tr-*`, `Te-*`) matches the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) by Masoud Nickparvar on Kaggle. The dataset itself is not included in this repo — download it separately and place it in `Training`/`Testing` folders to reproduce the notebook.

## Model

- **Architecture**: VGG16 (ImageNet weights, base frozen except last 3 layers) → Flatten → Dropout(0.3) → Dense(128, ReLU) → Dropout(0.2) → Dense(4, softmax)
- **Input size**: 128 × 128 × 3, pixel values normalized to [0, 1]
- **Training**: 15 epochs, Adam optimizer (lr=1e-4), batch size 20
- **Results**: 99.1% training accuracy, 97% test accuracy (weighted F1 0.97)

| Class | Precision | Recall | F1 |
|---|---|---|---|
| Glioma | 0.97 | 0.94 | 0.95 |
| Meningioma | 0.94 | 0.96 | 0.95 |
| No Tumor | 0.99 | 1.00 | 1.00 |
| Pituitary | 0.99 | 0.99 | 0.99 |

## Running the Notebook

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Download the [dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) and place it in `Training/` and `Testing/` folders (each with `glioma/`, `meningioma/`, `notumor/`, `pituitary/` subfolders) alongside the notebook.
3. Update the hardcoded `train_dir`/`test_dir` paths near the top of the notebook to point to your local dataset location.
4. Open `Brain_Tumor_Prediction1_beforewebsitemaking.ipynb` in Jupyter and run the cells in order.
5. To persist the trained model, uncomment the `model.save(...)` cell under **Model Saving and History saving**.

## Roadmap

- [ ] Save and commit the trained model (`.h5`)
- [ ] Build the Flask inference app (`main.py` + `templates/index.html`)
- [ ] Add sample test images for manual verification

## Disclaimer

This project is for educational and research purposes only. Predictions should not be used for actual medical diagnosis without professional medical review.
