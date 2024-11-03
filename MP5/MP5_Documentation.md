# Documentation

## Machine Problem: Object Detection and Recognition using YOLO 

* I downloaded a pre-trained yolo v3 model, as I was trying to follow the EXER 4 Example code as close as possible.

* I followed the code example in EXER 4 until I encountered problems with displaying it.
I kept on editing the code to hopefully get the boundary boxes to show in the images. 

List of things I added:
* code.names file to get labels for the dataset.
* another data processing definition (detect_objects) in order to utilize multiple given inputs 
* changed cv2.imshow since that line is disabled in google colab.
