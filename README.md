# Tomato Plant Disease Classifier

This project is a Flask web application that uses a trained deep learning model to classify tomato plant diseases from uploaded images. It provides predictions along with symptoms, remedies, and prevention information for the detected diseases.

# Dataset
This project uses the Tomato plant subset from the "Plant Village Dataset (Updated)" available on Kaggle. If you want to run the training script, you'll need to download this dataset.

Download the dataset from Kaggle: Plant Village Dataset (Updated)
Extract only the 'Tomato' folder from the downloaded dataset.
Place the 'Tomato' folder in the project directory. The project structure should look like this:
Copyproject_root/
├── Tomato/
│   ├── Train/
│   │   ├── Bacterial_spot/
│   │   ├── Early_blight/
│   │   ├── Healthy/
│   │   ├── Late_blight/
│   │   ├── Leaf_Mold/
│   │   ├── Septoria_leaf_spot/
│   │   ├── Spider_mites_Two_spotted_spider_mite/
│   │   ├── Target_Spot/
│   │   ├── Tomato_Yellow_Leaf_Curl_Virus/
│   │   └── Tomato_mosaic_virus/
│   ├── Test/
│   │   [Similar disease subfolders as in Train]
│   └── Val/
│       [Similar disease subfolders as in Train]
├── app.py
├── model.py
├── train.py
├── evaluation.py
└── ...


Note: The training script is configured to use this directory structure. If you change the location of the dataset, make sure to update the data_dir variable in the training script.

## Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.7+
- pip (Python package installer)

## Setup Instructions

1. Clone the repository:
   ```
   git clone <repository-url>
   cd <repository-name>
   ```

2. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```
   pip install flask torch torchvision pillow
   ```

4. Ensure you have the following files in your project directory:
   - `app.py`: The main Flask application
   - `model.py`: Contains functions to create and load the model
   - `best_model_fold_0.pth`: The trained model file
   - `remedies.json`: JSON file containing disease information
   - `templates/index.html`: HTML template for the web interface

## Running the Application

1. Start the Flask development server:
   ```
   python app.py
   ```

2. Open a web browser and navigate to `http://127.0.0.1:5000/`

3. Use the web interface to upload an image of a tomato plant leaf

4. The application will process the image and display the predicted disease along with additional information

## Project Structure

- `app.py`: Main Flask application file
- `model.py`: Contains model-related functions
- `best_model_fold_0.pth`: Trained model weights
- `remedies.json`: Disease information database
- `templates/index.html`: HTML template for the web interface

## Notes

- The model is trained to recognize the following tomato plant conditions:
  - Bacterial Spot
  - Early Blight
  - Healthy
  - Late Blight
  - Septoria Leaf Spot
  - Yellow Leaf Curl Virus

- Make sure your `remedies.json` file is properly formatted and contains information for all the above conditions

- The application uses CPU for inference. If you have a CUDA-enabled GPU, you can modify the code to use it for faster predictions

## Troubleshooting

If you encounter any issues:
1. Ensure all required packages are installed
2. Check that all necessary files are present in the correct directories
3. Verify that the model file path in `app.py` matches your actual model file name

For any other problems, please open an issue in the project repository.
