# DevdattKhilari-Deepfake-Recognition-using-AI-

# Deepfake Detection

### A Full-Stack Deepfake Detection Application developed FastAPI, Tensorflow, OpenCV, Next.js and Tailwind CSS

## To run this project locally:
#### Pre requisites: Python(>=3.10), Node.js(>=18.19)

* Clone this repository
```
git clone 
cd deepfake-detection
```
* Setup python virtual environment and install dependencies
```
python3 -m venv ./venv
source ./venv/bin/activate
pip install -r requirements.txt
```
* Install frontend dependencies (present inside cilent directory)
```
cd client
npm install
```

* Go to parent directory (where app.py is located) and run the FastAPI server using:
```
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```
Now our FastAPI server must be running on localhost:8000 (make sure that your port 8000 is free before running previous command).

* Go to client directory and create another terminal (where package.json is located) and run the React App using:
```
npm run dev
```
Now our React App must be running on localhost:5173 (or on any port >5173 if it is not free).


## Project description
This AI-powered deepfake recognition system detects manipulated images and videos by analyzing facial inconsistencies, unnatural movements, and pixel-level artifacts. Built with FastAPI, TensorFlow, OpenCV, and React.js, it leverages a deep CNN model to achieve high accuracy in identifying deepfakes.

   ### Model Structure
   * The deepfake detection model is a 10-layer Convolutional Neural Network (CNN) optimized for image and video classification.
   * It consists of 653k+ parameters with dropout regularization (0.5) to prevent overfitting by ensuring independent learning among neurons.
   * Initial convolution layers use a kernel size of 5 with 64 filters, followed by max-pooling, while later layers have fewer filters and a dilation rate of 2 to expand the receptive field.
   * Dilated convolutions are applied in the final three layers, enhancing feature extraction for detecting subtle deepfake artifacts..
   *The model performs binary classification with sigmoid activation to distinguish real from fake media.
   * The input image size is [224,224,3], ensuring optimal feature extraction.
   * The model achieves >99.9% training accuracy and >99% validation accuracy, demonstrating high effectiveness in detecting deepfakes.


<img src="client/public/model_structure.png"/>


## Performance Analysis

* **Training Logs**
<img src="client/public/logs.png"/>

* **Evaluation Metrics: Accuracy, Precision, Recall**
<img src="client/public/score1.png"/>
<img src="client/public/score2.png"/>

* **Confusion Matrix**
    * True Positive: 602
    * False Positive: 7
    * False Negative: 5
    * True Negative: 586
    <br/>
    <img src="client/public/confusion_matrix.png" style="height:300px; width:300px; display:block margin-bottom:100px;"/>


* **ROC-AUC curve**
<img src="client/public/ROC.png"/>


## Post-Training Pipeline
<img src="client/public/pipeline.png"/>

## Application Architecture (Client-Server)
<img src="client/public/application_architecture.png">


## Screenshots
<img src="client/public/df1.png"/>
<img src="client/public/df2.png"/>
<img src="client/public/df3.png"/>
<img src="client/public/df5.png"/>
<img src="client/public/df4.png"/>
