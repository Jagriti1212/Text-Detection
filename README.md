1. Install Requirements-
torch==0.4.1.post2
torchvision==0.2.1
opencv-python==3.4.2.17
scikit-image==0.14.2
scipy==1.1.0
lmdb
pillow
nltk
natsort

2. Run the following Command to get the score maps and the results for text detection-
!python3 Pipeline/pipeline.py --trained_model=Pipeline/craft_mlt_25k.pth --test_folder=Pipeline/test/
The score maps will be saved in the Pipeline/results folder and the bounding box coordinates of the detected words for every image will be saved in the data.csv file

3.Run the below command to crop the detected words for every image-
!python3 Pipeline/pipeline.py
The cropped words for every image will be saved in the Pipeline/Crop Words folder.

4.Run the follwing command to save the recognized words to data.csv file.
!python3 Pipeline/craft_recog.py \
--Transformation None --FeatureExtraction VGG --SequenceModeling BiLSTM --Prediction CTC \
--image_folder 'Pipeline/Crop Words' \
--saved_model Pipeline/None-VGG-BiLSTM-CTC.pth

