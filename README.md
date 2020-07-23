# Face-Detection-Model-using-Caffemodel
Face Detection Model which detects faces using caffemodel-a face detector based on deep learning, owned by openCV.
This code has been run on Ubuntu 18.0.4 LTS system. I dont know the exact way of running this code on windows or jupyter, but 
learning on Ubuntu or Linux is recommended for DL projects. 
This model has the capacity to detect images using an openCV based face detector called caffemodel. The model initially reads the image,
creates a blob.
Blobbing has 3 steps- 
  Mean subtraction: The RGB colors of input image is subtracted from its means RGB values.
  Scaling-The result of above operation is divided by some scaling factor for normalization
  Channel Swapping- often openCV considers BGR as image's color values, but the mean considers RGB. So to avoid this confusion swapping is done 
                    between R and B.
After the blob is created, the features are extracted using the caffemodel, which are then used for detection of face.The model has an additional input 
for confidence level, due to which the model ignores all face detections below that value.
