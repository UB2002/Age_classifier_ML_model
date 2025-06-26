# Age Regression from Face Images

This project implements a deep learning model to predict a person's age from their face image using PyTorch and a ResNet18 backbone. The model is trained as a regression task, outputting a continuous age value.

## Project Overview
- **Task:** Predict the age of a person from a face image (regression, not classification)
- **Model:** ResNet18 backbone with custom regression head
- **Loss Function:** L1 Loss (Mean Absolute Error)
- **Metrics:** MAE, accuracy within ±5 and ±10 years
- **Data:** Images organized in folders by age (e.g., `data/train/25/image1.jpg`)

## Setup Instructions

1. **Clone the repository and navigate to the project directory:**
   ```bash
   git clone https://github.com/UB2002/Re-identification_Model.git
   ```

2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On Linux/Mac:
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Prepare your data:**
   - Organize your dataset as follows:
     ```
     data/
       train/
         20/
           image1.jpg
           image2.jpg
           ...
         30/
           ...
       val/
         20/
           ...
         30/
           ...
     ```
   - Each folder under `train` and `val` should be named with the age label and contain images of faces of that age.

## Model Architecture Overview
- **Backbone:** ResNet18 (pretrained on ImageNet)
- **Head:**
  - Dropout(0.5)
  - Linear(num_features, 256) + ReLU
  - Dropout(0.3)
  - Linear(256, 128) + ReLU
  - Linear(128, 1)  # Output: predicted age

## Training
- Run the training script:
  ```bash
  run the notebook
  ```
- The script will train the model, print progress, and save the best model as `best_age_regressor.pth`.
- Training and validation loss/accuracy curves will be saved as `training_history.png`.

## Evaluation
- After training, the script will evaluate the model on the validation set and plot:
  - Loss over epochs
  - Accuracy within ±5 years over epochs
  - Predicted vs. true age scatter plot

## Predicting Age for a New Image
- Use the `predict_age` function in `main.py` or `model.ipynb`:
  ```python
  predicted_age = predict_age('best_age_regressor.pth', 'path/to/your/image.jpg')
  print(f'Predicted age: {predicted_age:.1f} years')
  ```
