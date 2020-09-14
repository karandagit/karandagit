# OpenCV
  
  -> OpenCV-Python is a library of Python bindings designed to solve computer vision problems.
  
## Image Processing topics in OpenCV

    -> Geometric Transformations of Images
    -> Image Thresholding
    -> Morphological Transformations
    -> Canny Edge Detection
    -> Contours in OpenCV
    -> Histograms in OpenCV
    
## Object Detection topics in OpenCV

    -> Cascade Classifier :- Object Detection using Haar feature-based cascade classifiers is an effective object detection method.
                             It is basically a machine learning based approach where a cascade function is trained from a lot of positive and negative images. It is then used to detect objects in other images.
                             
# Getting Started with Images

    -> functions : cv2.imread(), cv2.imshow() , cv2.imwrite()
    
## Read an image

    Use the function cv2.imread() to read an image. The image should be in the working directory or a full path of image should be given. 
    Second argument is a flag which specifies the way image should be read.
        • cv2.IMREAD_COLOR : Loads a color image. Any transparency of image will be neglected. It is the defaultflag.
        • cv2.IMREAD_GRAYSCALE : Loads image in grayscale mode
        • cv2.IMREAD_UNCHANGED : Loads image as such including alpha channel
        
        Instead of these three flags, you can simply pass integers 1, 0 or -1 respectively.
        
## Display an image        

    -> Use the function cv2.imshow() to display an image in a window. The window automatically fits to the image size.
       First argument is a window name which is a string. second argument is our image. You can create as many window as you wish, but with different window names.
       
    -> cv2.waitKey() is a keyboard binding function. Its argument is the time in milliseconds. The function waits for specified milliseconds for any keyboard event.   
    
    -> cv2.destroyAllWindows() simply destroys all the windows we created. If you want to destroy any specific window, use the function cv2.destroyWindow() where you pass the exact window name as the argument.
    
## Write an image  

   -> Use the function cv2.imwrite() to save an image.
      First argument is the file name, second argument is the image you want to save.
