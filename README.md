This repo contains my trained models for Kaggle Competition - [TF Barrier Reef Challenge](https://www.kaggle.com/c/tensorflow-great-barrier-reef)

Used Ultralytics/Yolov5 weights to re-train on Challenge Dataset.

## Train Track/History
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

## Challenge Track/History
- First submission 
	- Date : 14/Dec/2021
	- Model : Yolov5l
	- Dataset : default, original with annotation
	- My score : 0.325 
	- Leaderboard Rank #1 score : 0.619 as of 16/Dec/2021
