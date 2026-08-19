# Brain Tumor Prediction System

A machine learning-powered web application for detecting and classifying brain tumors from MRI images. This system uses a pre-trained deep learning model to analyze medical imaging and identify tumor types with confidence scores.

## Features

- **MRI Image Analysis**: Upload and analyze brain MRI images
- **Tumor Classification**: Automatically classifies tumors into 4 categories:
  - Glioma
  - Meningioma
  - Pituitary
  - No Tumor
- **Confidence Scoring**: Displays prediction confidence percentage for each result
- **Web-Based Interface**: User-friendly Bootstrap UI for easy access
- **Real-Time Results**: Instant predictions with visual feedback
- **Image Display**: Shows uploaded images alongside prediction results

## Technology Stack

- **Backend**: Flask (Python)
- **Deep Learning**: TensorFlow/Keras
- **Frontend**: HTML5, Bootstrap 5, JavaScript
- **Model**: Pre-trained Convolutional Neural Network (CNN)
- **Image Processing**: PIL/Pillow

## Project Structure

```
Brain_Tumor_Prediction/
├── main.py                                    # Flask application
├── Brain_Tumor_Prediction.h5                 # Pre-trained model
├── Brain_Tumor_Prediction1_beforewebsitemaking.ipynb  # Training notebook
├── templates/
│   └── index.html                            # Web interface
├── uploads/                                  # Uploaded image storage
├── Training/                                 # Training data
│   ├── glioma/
│   ├── meningioma/
│   ├── notumor/
│   └── pituitary/
├── Testing/                                  # Test data
│   ├── glioma/
│   ├── meningioma/
│   ├── notumor/
│   └── pituitary/
├── Verify/                                   # Verification data
├── Updates/                                  # Additional resources
└── Some More testing photoss/                # Extra test images
```

## Getting Started

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Installation

1. **Clone or navigate to the project directory**
   ```bash
   cd "Brain tumor prediction project"
   ```

2. **Install required dependencies**
   ```bash
   pip install flask tensorflow keras pillow numpy
   ```

3. **Verify the model file exists**
   - Ensure `Brain_Tumor_Prediction.h5` is in the project root directory

### Running the Application

1. **Start the Flask server**
   ```bash
   python main.py
   ```

2. **Access the web interface**
   - Open your browser and navigate to: `http://localhost:5000`

3. **Upload an MRI image**
   - Click the upload button and select a brain MRI image (PNG, JPG, etc.)
   - The system will analyze the image and display results within seconds

## Model Details

- **Input Size**: 128 × 128 pixels
- **Image Normalization**: Pixel values normalized to [0, 1]
- **Output Classes**: 4 tumor types
- **Confidence Threshold**: Shows confidence percentage for predictions

## Usage

1. **Upload MRI Image**: Select a brain MRI scan from your device
2. **Wait for Analysis**: The model processes the image (typically < 5 seconds)
3. **View Results**: 
   - Prediction: Tumor type or "No Tumor"
   - Confidence: Percentage confidence of the prediction
   - Uploaded Image: Displayed for verification

## Training and Validation

- The project includes training data organized by tumor type
- Training notebook: `Brain_Tumor_Prediction1_beforewebsitemaking.ipynb`
- The model is pre-trained and ready for inference
- Test and verification folders contain sample images for evaluation

## Configuration

**Main Parameters** (in `main.py`):
- `IMAGE_SIZE`: 128 (input image size)
- `UPLOAD_FOLDER`: './uploads' (location for storing uploaded images)
- `model`: 'Brain_Tumor_Prediction.h5' (trained model file)

## Notes

- Uploaded images are stored in the `uploads/` folder
- The model requires exact input size (128×128) - images are resized automatically
- Predictions should be verified by medical professionals for actual clinical use
- This tool is for educational and research purposes

## Model Classes

| Class | Description |
|-------|-------------|
| Glioma | Most common type of brain tumor originating from glial cells |
| Meningioma | Tumor arising from meninges (membrane around brain) |
| Pituitary | Tumor in the pituitary gland |
| No Tumor | No tumor detected in the MRI image |

## Troubleshooting

- **Model not found**: Ensure `Brain_Tumor_Prediction.h5` is in the project directory
- **Port already in use**: Change the port in `main.py`: `app.run(debug=True, port=5001)`
- **Image upload fails**: Ensure the image format is supported (PNG, JPG, JPEG)
- **Import errors**: Run `pip install --upgrade tensorflow keras`

## Resources

- Training and testing data are organized in folders by tumor type
- The notebook provides detailed information on model training methodology
- Example images are available in the Testing and Training folders

## Disclaimer

This project is for educational and research purposes only. The predictions should not be used for actual medical diagnosis without professional medical review. Always consult with qualified medical professionals for any medical concerns.

## Development

To retrain or modify the model:
1. Open `Brain_Tumor_Prediction1_beforewebsitemaking.ipynb`
2. Prepare your dataset in the Training folder
3. Run the notebook cells to train the model
4. Save the new model as `Brain_Tumor_Prediction.h5`
