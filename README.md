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
![maxresdefault](https://user-images.githubusercontent.com/64326560/89098012-92bae880-d401-11ea-9843-bfa810cdcd70.jpg)
![911831-kritisanon-motivationalquote](https://user-images.githubusercontent.com/64326560/89098013-9484ac00-d401-11ea-902b-5e9d8ebff5b7.jpg)
![ayushsu1-1592394645](https://user-images.githubusercontent.com/64326560/89098015-951d4280-d401-11ea-9c60-c6c91a04ae6d.jpg)
![DwnavjPUYAAqEh2](https://user-images.githubusercontent.com/64326560/89098017-95b5d900-d401-11ea-8919-346e6f6fc76c.jpg)
![kriti_3](https://user-images.githubusercontent.com/64326560/89098036-c3028700-d401-11ea-85b7-5e33ff257938.jpg)
![modi_2](https://user-images.githubusercontent.com/64326560/89098038-c433b400-d401-11ea-948b-517fa9963ae1.jpg)
![sush_1](https://user-images.githubusercontent.com/64326560/89098039-c4cc4a80-d401-11ea-8056-c0b9da8e4634.jpg)
![ayushmaan_1](https://user-images.githubusercontent.com/64326560/89098040-c564e100-d401-11ea-880e-ce277980e451.jpg)
![carry_1](https://user-images.githubusercontent.com/64326560/89098042-c564e100-d401-11ea-8914-728c16aabc3b.jpg)
![deep_1](https://user-images.githubusercontent.com/64326560/89098044-c5fd7780-d401-11ea-828f-a74ae63feb1c.jpg)
