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
For executing the code-
  test image 2 - python3 face_detection.py -i test_pic2.jpg -p deploy.prototxt.txt -m res10_300x300_ssd_iter_140000.caffemodel 
  test image 1 - python3 face_detection.py -i face_detection/images/AG/00005.png -p deploy.prototxt.txt -m res10_300x300_ssd_iter_140000.caffemodel -c 0.51
  
I have added codes for detecting faces from webcam, as well as video files, and improving the fps rate compared to the naive process. For improvement, I have 
used another separate thread for read() operation of cv2, so that it wont block other operations from happening in the main thread, and hence fps will increase.
For executing the code-
  video file code - python3 face_detection_vstream.py -p deploy.prototxt.txt -m res10_300x300_ssd_iter_140000.caffemodel -v Videos/avengers2.mp4
  webcam video file - python3 fps_improved.py -p deploy.prototxt.txt -m res10_300x300_ssd_iter_140000.caffemodel -d 1
