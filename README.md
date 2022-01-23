This repo contains my trained models for Kaggle Competition - [TF Barrier Reef Challenge](https://www.kaggle.com/c/tensorflow-great-barrier-reef)

Used Ultralytics/Yolov5 weights to re-train on Challenge Dataset.

> NOTE 1: all weights of training are on my Kaggle account private dataset.

> NOTE 2: weights for "s" model are added, as they are under 100mb

> NOTE 3: all training is done on Kaggle Free GPU quota of 36 hours/week

> NOTE 4: only the best submission data is logged here

## [Leaderboard Scores](https://www.kaggle.com/c/tensorflow-great-barrier-reef/leaderboard)
- [23 Jan 2022] 1st Competitor : 0.779 || My Score : 0.520
- [17 Jan 2022] 1st Competitor : 0.720 || My Score : 0.520
- [15 Jan 2022] 1st Competitor : 0.692 || My Score : 0.520
- [02 Jan 2022] 1st Competitor : 0.673 || My Score : 0.513
- [02 Jan 2022] 1st Competitor : 0.672 || My Score : 0.513
- [30 Dec 2021] 1st Competitor : 0.658 || My Score : 0.512
- [26 Dec 2021] 1st Competitor : 0.658 || My Score : 0.502
- [20 Dec 2021] 1st Competitor : 0.619 || My Score : 0.488
- [19 Dec 2021] 1st Competitor : 0.619 || My Score : 0.473
- [16 Dec 2021] 1st Competitor : 0.619 || My Score : 0.325

## Challenge Submission Score Log
- **First submission**
	- Date : 14/Dec/2021
	- Model : Yolov5l
	- Dataset : default, original with annotation
	- **My score : 0.325**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.619

- **Second submission**
	- Summary : Model Ensembling, with 1st model running on original images and 2nd running on enhanced images with different Conf + IOU thresholds for each model. Results of both models are fused using [Weighted-Boxes-Fusion](https://github.com/ZFTurbo/Weighted-Boxes-Fusion)
	- Date : 19/Dec/2021
	- Model : Yolov5l (previous) + Yolov5l (retrained on enchanced images at 1280)
	- Dataset : Original + Enhanced Images
	- **My score : 0.473**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.619

- **Third submission**
	- Summary : Model Ensembling with "Test Time Augment" set to false and threshold tuned, 3 models are used. Results of both models are fused using [Weighted-Boxes-Fusion](https://github.com/ZFTurbo/Weighted-Boxes-Fusion)
	- Date : 20/Dec/2021
	- Model : Yolov5l (previous) + Yolov5l (retrained on enchanced images at 1280) + Yolov5l (retrained on enchanced images at 1280)
	- Dataset : Original + Enhanced Images
	- **My score : 0.488**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.619

- **Fourth submission**
	- Summary : Model ensembling + new image pre-processing 
	- Date : 26/Dec/2021
	- Model : Yolov5l (previous) + Yolov5l6 (retrained on new CLAHE processed images at 1280)x2
	- Dataset : New Enhanced Images
	- **My score : 0.502**
	- Device : GPU
	- Leaderboard Rank #1 score : 0.658

- **Fifth submission**
	- Same as previous with params modifications.
	- Date : 30/Dec/2021
	- **My score : 0.512**

- **Sixth submission**
	- Param modifications
	- Date : 26/Jan/2022
	- **My score : 0.520**

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

- "yolov5l6 train"
	- Model trained : Yolov5l6
	- Trained on Image Size : 1280
	- Epochs : -
	- Dataset details : Trained on new ehanced+augmented data.

- "yolov5s6 train"
	- Model trained : Yolov5s6
	- Trained on Image Size : 1280
	- Epochs : 40
	- Dataset details : Trained on new ehanced+augmented data.