This repo contains my trained models for Kaggle Competition - [TF Barrier Reef Challenge](https://www.kaggle.com/c/tensorflow-great-barrier-reef)

Used Ultralytics/Yolov5 weights to re-train on Challenge Dataset.

> NOTE : all weights of training are on Kaggle account private dataset.

## Challenge Submission Score Log
- **First submission**
	- Date : 14/Dec/2021
	- Model : Yolov5l
	- Dataset : default, original with annotation
	- **My score : 0.325**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.619 as of 16/Dec/2021

- **Second submission**
	- Summary : Model Ensembling, with 1st model running on original images and 2nd running on enhanced images with different Conf + IOU thresholds for each model. Results of both models are fused using [Weighted-Boxes-Fusion](https://github.com/ZFTurbo/Weighted-Boxes-Fusion)
	- Date : 19/Dec/2021
	- Model : Yolov5l (previous) + Yolov5l (retrained on enchanced images at 1280)
	- Dataset : Original + Enhanced Images
	- **My score : 0.473**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.619 as of 19/Dec/2021

- **Third submission**
	- Summary : Model Ensembling with "Test Time Augment" set to false and threshold tuned, 3 models are used. Results of both models are fused using [Weighted-Boxes-Fusion](https://github.com/ZFTurbo/Weighted-Boxes-Fusion)
	- Date : 20/Dec/2021
	- Model : Yolov5l (previous) + Yolov5l (retrained on enchanced images at 1280) + Yolov5l (retrained on enchanced images at 1280)
	- Dataset : Original + Enhanced Images
	- **My score : 0.488**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.619 as of 19/Dec/2021

## Model Train Log
- "yolov5l train 1"
	- Model trained : Yolov5l
	- Trained on Image Size : 1024
	- Epochs : 15
	- Dataset details : Trained on original data. Only images with annotations were used. No image preprocessing is used.

- "yolov5x6 train 1" (This is a saved checkpoint)
	- Model trained : Yolov5x6
	- Trained on Image Size : 1024
	- Epochs : 7
	- Dataset details : Trained on enhanced images. Images with/without annotations were used.

- "yolov5l train 2"
	- Model trained : Yolov5l (train1 weights)
	- Trained on Image Size : 1280
	- Epochs : 12
	- Dataset details : Trained on ehanced+augmented data.