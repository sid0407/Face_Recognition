# Face_Recognition
Face detection and recognition into 6 classes of some famous personalities.
## Step 1: Dataset collection -
**Train Data**<br/><br/>
Gathered 60 images of famous celebrities for training set.<br/>
**Validation Data**<br/><br/>
Gathered 18 images of the same celebrities for the validation set.
## Step 2: Detect Faces -
Using `dlib cnn face detector` find faces in image and crop faces and store them in separate folders sorting by individual person.
Download 'mmod_human_face_detector' to use as 'dlib cnn face detector'<br/>
```
! wget http://dlib.net/files/mmod_human_face_detector.dat.bz2 
!bzip2 -dk mmod_human_face_detector.dat.bz2
```
The directory structure should look like this -
```
Directory structure :
|Images /
|  |-- (60 images)
|Images_crop /
|  |--ayushmaan/
|     |--(10 images)
|  |--carry/ 
|     |--(10 images)
|  |--deep/ 
|         |--(10 imgaes)
|  |-- sush/ (10 images)
|  |--kriti / (10 images) 
|  |--modi / (10 images)
|Images_test / 
|  |-- .. / (18 images)
|Images_test_crop / 
|  |--ayushmaan / (3 images)
|  |--carry / (3 images)
|  |--deep / (3 imgaes)
|  |--kriti / (3 images)
|  |--modi / (3 images)
|  |--sush / (3 images) 
|Upload_your_images /
|  |--Here you can put your own images to test the model
|Your_predictions /
|  |--The result
|Face_Recognition.ipynb
|mmod_human_face_detector.dat
```
## Step 3: Download the model weights
Download weights using 
`! gdown https://drive.google.com/uc?id=1CPSeum3HpopfomUEK1gybeuIVoeJT_Eo` <br/>
Define vgg-face model architecture and load weights.
## Step 4: Train Softmax regressor for 6 person classification from embeddings.
Prepare train data and test data from the embeddings and feed into a simple softmax regressor with 3 layers containing first layer with 100 units and tanh activation function , second layer with 10 units and tanh activation function and third layer with 6 units for each person with softmax activation.<br/>
<br/>**Predictions**<br/>
For an image(may contain multiple faces) extract each face,get embeddings,get prediction from classifier network,make bounding box around face and write person name.<br/><br/>
**Some Predicted Image Results**<br/>

