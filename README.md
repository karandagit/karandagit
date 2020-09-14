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
      
## Erosion and Dilation of images using OpenCV in python

    -> Morphological operations are a set of operations that process images based on shapes. They apply a structuring element to an input image and generate an output image.
       The most basic morphological operations are two: Erosion and Dilation
       
       Basics of Erosion:
        -> Erodes away the boundaries of foreground object
        -> Used to diminish the features of an image.
        
        Basics of Dilation:
          -> Increases the object area
          -> Used to accentuate features
          
## Uses of Erosion and Dilation:
    
    Erosion:
      It is useful for removing small white noises.
      Used to detach two connected objects etc.
    
    Dilation:
      In cases like noise removal, erosion is followed by dilation. Because, erosion removes white noises, but it also shrinks our object. So we dilate it. Since noise is gone, they won’t come back, but our object area increases.
      It is also useful in joining broken parts of an object.
      
## Thresholding techniques using OpenCV

    1. Simple Thresholding :-
        The basic Thresholding technique is Binary Thresholding. For every pixel, the same threshold value is applied. If the pixel value is smaller than the threshold, it is set to 0, otherwise, it is set to a maximum value.
        
       The different Simple Thresholding Techniques are:
        -> cv2.THRESH_BINARY: If pixel intensity is greater than the set threshold, value set to 255, else set to 0 (black).
        -> cv.THRESH_TRUNC: If pixel intensity value is greater than threshold, it is truncated to the threshold. The pixel values are set to be the same as the threshold. All other values remain the same.
        -> cv.THRESH_TOZERO: Pixel intensity is set to 0, for all the pixels intensity, less than the threshold value.
        
    2. Adaptive Thresholding :-
        Adaptive thresholding is the method where the threshold value is calculated for smaller regions. This leads to different threshold values for different regions with respect to the change in lighting. We use cv2.adaptiveThreshold for this.
        
        Syntax: cv2.adaptiveThreshold(source, maxVal, adaptiveMethod, thresholdType, blocksize, constant)
        
        Parameters:
          -> source: Input Image array(Single-channel, 8-bit or floating-point)
          -> maxVal: Maximum value that can be assigned to a pixel.
          -> adaptiveMethod: Adaptive method decides how threshold value is calculated.
          
          cv2.ADAPTIVE_THRESH_MEAN_C: Threshold Value = (Mean of the neighbourhood area values – constant value). In other words, it is the mean of the blockSize×blockSize neighborhood of a point minus constant.
          
          cv2.ADAPTIVE_THRESH_GAUSSIAN_C: Threshold Value = (Gaussian-weighted sum of the neighbourhood values – constant value). In other words, it is a weighted sum of the blockSize×blockSize neighborhood of a point minus constant.
            -> thresholdType: The type of thresholding to be applied.
            -> blockSize: Size of a pixel neighborhood that is used to calculate a threshold value.
             -> constant: A constant value that is subtracted from the mean or weighted sum of the neighbourhood pixels.
        
