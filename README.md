1.Install Requirements-<br />
torch==0.4.1.post2<br />
torchvision==0.2.1<br />
opencv-python==3.4.2.17<br />
scikit-image==0.14.2<br />
scipy==1.1.0<br />
lmdb<br />
pillow<br />
nltk<br />
natsort<br />

2.Run the following Command to get the score maps and the results for text detection-<br />
!python3 Pipeline/pipeline.py --trained_model=Pipeline/craft_mlt_25k.pth --test_folder=Pipeline/test/<br />
The score maps will be saved in the Pipeline/results folder and the bounding box coordinates of the detected words for every image will be saved in the data.csv file<br />

3.Run the below command to crop the detected words for every image-<br />
!python3 Pipeline/pipeline.py<br />
The cropped words for every image will be saved in the Pipeline/Crop Words folder.<br />

4.Run the follwing command to save the recognized words to data.csv file.<br />
!python3 Pipeline/craft_recog.py \
--Transformation None --FeatureExtraction VGG --SequenceModeling BiLSTM --Prediction CTC \
--image_folder 'Pipeline/Crop Words' \
--saved_model Pipeline/None-VGG-BiLSTM-CTC.pth

