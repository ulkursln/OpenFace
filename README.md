## What's new in modified version

Following features are added: 

	* allowing manual AOI annotation and outcome visualization with newly proposed input parameters, 
	* enabling tracking with custom detector, 
	* generating separated output files according to the input parameters and, 
 	* providing function to export frames in a video.  
	
####Instructions to use added features:
 
 **Tracking with defaul detector** 
 
	-f $video-file -outroot $output-directory -doTracking $0/1 -detectedFaces $file-name (Eg: -f Rec_01.avi -outroot \1 -doTracking 
	0 -detectedFaces \\detectedFaces.txt)
		add further arguments to not create following output files:  -no2Dfp -no3Dfp -noAUs -noPose -noGaze -noMparams
		-doTracking 0:do tot visualize tracking, 1:visualize tracking

 **Tracking with pre-trained detector**
 
	-f $video-file -outroot $output-directory -doTracking $0/1 -detector #face-detectore-file -detectedFaces $file-name 
	
	(Eg: -f Rec_01.avi -outroot \1 -doTracking 0 -detector \face_detector_1.svm  -detectedFaces \\detectedFaces.txt)
		add further arguments to not create following output files:  -no2Dfp -no3Dfp -noAUs -noPose -noGaze -noMparams
		-doTracking 0:do not visualize tracking, 1:visualize tracking

**Label AOI manually**

	-manualAOILabeling  -cpf $output-file -f $video-file -lf $2dlandmark-file -tfd $raw-gazeData-file -aoi $aoi-file -etiWidth
	$eyetrackerImageWidth -etiHeight $eyetrackerImageHeight -confidence $confidenceThreshold -eteX $eye_tracker_error_width -eteY
	$eye_tracker_error_height -sf $startingFrameNo -ef $endingFrameNo
	
	(Eg: -manualAOILabeling -cpf \correctedFrames.txt -f Rec_01.avi -lf \2d_landmarks.txt -lf \tobiiFilledData_1.txt -aoi
	\faceAsAOI.txt -etiWidth 640 -etiHeight 480 -confidence 0.7 -eteX 4.8 -eteY 5.2)

**Review Outcomes**

	-showResults -f $video-file -lf $2dlandmark-file -tfd $raw-gazeData-file -aoi $aoi-file -etiWidth $eyetrackerImageWidth 
	-etiHeight $eyetrackerImageHeight -confidence $confidenceThreshold -eteX $eye_tracker_error_width -eteY 	
	$eye_tracker_error_height -sf $startingFrameNo -ef $endingFrameNo
			
	(Eg: -showResults -f Rec_01.avi -lf \2d_landmarks.txt -lf \tobiiFilledData_1.txt -aoi \faceAsAOI.txt -etiWidth 640 -etiHeight
	480 -confidence 0.7 -eteX 4.8 -eteY 5.2)

**Extract Frames**

	-exportFrames $fileName $folderName (Eg: -exportFrames Rec_01.avi \exportedFrames

# OpenFace: an open source facial behavior analysis toolkit

[![Build Status](https://travis-ci.org/TadasBaltrusaitis/OpenFace.svg?branch=master)](https://travis-ci.org/TadasBaltrusaitis/OpenFace)
[![Build status](https://ci.appveyor.com/api/projects/status/8msiklxfbhlnsmxp/branch/master?svg=true)](https://ci.appveyor.com/project/TadasBaltrusaitis/openface/branch/master)

Over the past few years, there has been an increased interest in automatic facial behavior analysis and understanding. We present OpenFace – an open source tool intended for computer vision and machine learning researchers, affective computing community and people interested in building interactive applications based on facial behavior analysis. OpenFace is the ﬁrst open source tool capable of facial landmark detection, head pose estimation, facial action unit recognition, and eye-gaze estimation. The computer vision algorithms which represent the core of OpenFace demonstrate state-of-the-art results in all of the above mentioned tasks. Furthermore, our tool is capable of real-time performance and is able to run from a simple webcam without any specialist hardware.

The code was written mainly by Tadas Baltrusaitis during his time at the Language Technologies Institute at the Carnegie Mellon University; Computer Laboratory, University of Cambridge; and Institute for Creative Technologies, University of Southern California.

Special thanks goes to Louis-Philippe Morency and his MultiComp Lab at Institute for Creative Technologies for help in writing and testing the code, and Erroll Wood for the gaze estimation work.

**For instructions of how to install/compile/use the project please see [wiki](https://github.com/TadasBaltrusaitis/OpenFace/wiki)**

More details about the project - http://www.cl.cam.ac.uk/research/rainbow/projects/openface/


## Functionality

The system is capable of performing a number of facial analysis tasks:

- Facial Landmark Detection

![Sample facial landmark detection image](https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/multi_face_img.png)

- Facial Landmark and head pose tracking (links to YouTube videos)

<a href="https://www.youtube.com/watch?v=V7rV0uy7heQ" target="_blank"><img src="http://img.youtube.com/vi/V7rV0uy7heQ/0.jpg" alt="Multiple Face Tracking" width="240" height="180" border="10" /></a>
<a href="https://www.youtube.com/watch?v=vYOa8Pif5lY" target="_blank"><img src="http://img.youtube.com/vi/vYOa8Pif5lY/0.jpg" alt="Multiple Face Tracking" width="240" height="180" border="10" /></a>

- Facial Action Unit Recognition

<img src="https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/au_sample.png" height="280" width="600" >

- Gaze tracking (image of it in action)

<img src="https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/gaze_ex.png" height="378" width="567" >

- Facial Feature Extraction (aligned faces and HOG features)

![Sample aligned face and HOG image](https://github.com/TadasBaltrusaitis/OpenFace/blob/master/imgs/appearance.png)

## Citation

If you use any of the resources provided on this page in any of your publications we ask you to cite the following work and the work for a relevant submodule you used.

####Overall system

**OpenFace: an open source facial behavior analysis toolkit**
Tadas Baltrušaitis, Peter Robinson, and Louis-Philippe Morency,
in *IEEE Winter Conference on Applications of Computer Vision*, 2016  

#### Facial landmark detection and tracking

**Constrained Local Neural Fields for robust facial landmark detection in the wild**
Tadas Baltrušaitis, Peter Robinson, and Louis-Philippe Morency. 
in IEEE Int. *Conference on Computer Vision Workshops, 300 Faces in-the-Wild Challenge*, 2013.  

#### Eye gaze tracking

**Rendering of Eyes for Eye-Shape Registration and Gaze Estimation**
Erroll Wood, Tadas Baltrušaitis, Xucong Zhang, Yusuke Sugano, Peter Robinson, and Andreas Bulling 
in *IEEE International. Conference on Computer Vision (ICCV)*,  2015 

#### Facial Action Unit detection

**Cross-dataset learning and person-specific normalisation for automatic Action Unit detection**
Tadas Baltrušaitis, Marwa Mahmoud, and Peter Robinson 
in *Facial Expression Recognition and Analysis Challenge*, 
*IEEE International Conference on Automatic Face and Gesture Recognition*, 2015 

# Final remarks

I did my best to make sure that the code runs out of the box but there are always issues and I would be grateful for your understanding that this is research code and not a commercial level product. However, if you encounter any problems/bugs/issues please contact me on github or by emailing me at Tadas.Baltrusaitis@cl.cam.ac.uk for any bug reports/questions/suggestions. 

# Copyright

Copyright can be found in the Copyright.txt

You have to respect boost, TBB, dlib, and OpenCV licenses.

