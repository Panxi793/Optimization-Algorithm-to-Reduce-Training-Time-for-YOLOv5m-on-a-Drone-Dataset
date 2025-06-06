# Optimization-Algorithm-to-Reduce-Training-Time-for-YOLOv5m-on-a-Drone-Dataset

## Introduction
This repository contains the implementation of the Yolo5 model for drone detection, replicating the results presented in the paper titled "Optimization Algorithm to Reduce Training Time for Yolo5". The project includes both the original and preprocessed datasets, along with the training scripts used to achieve the results.

## Dataset Information
- **Original Dataset**: 16,363 images
- **Preprocessed Dataset**: 13,368 images
- **Total Size**: Approximately 124 GB

Due ot the size, I only uploaded 1 sub-dataset out of the 12. If you would like to download the datasets, please contact me.

## Requirements
To run this project, you will need the following:

- Python 3.x
- PyTorch
- Other dependencies as specified in the `requirements.txt` file

You can create a virtual environment and install the required packages using:

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate

# Install required packages
pip install -r requirements.txt
```

## Setup Instructions for Yolo5 Repository
1. Clone the Yolo5 repository:
   ```bash
   git clone https://github.com/ultralytics/yolov5.git
   cd yolov5
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the pre-trained weights:
   - Place the `yolov5m.pt` file in the root directory of the Yolo5 repository.

4. Prepare the dataset:
   - Place your dataset in the `dataset/` directory.
   - Ensure the dataset is structured as required by the Yolo5 model.

5. Run the training script:
   ```bash
   python train.py --data yolo_configs/drone_preprocessed/drone_preprocessed.yaml --epochs 20 --batch-size 8 --weights yolov5m.pt --device 0 --project runs/train --name preprocessed_drone_yolov5m --save-period -1
   ```

## Results
The results of the training can be found in the `runs/` directory. The performance metrics for both the original and preprocessed datasets are summarized in the `documentation.txt` file.
