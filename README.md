# OcularDiseaseRecognition
This study focuses on the recognition of ocular diseases from fundus images using a combination of generic image preprocessing techniques and state-of-the-art convolutional neural network (CNN) models with transfer learning. The aim is to accurately identify and classify various ocular diseases, including Normal, Diabetes, Glaucoma, Cataract, AMD, Hypertension, Myopia, and Others.

To improve the quality of fundus images and facilitate the identification of disease-specific features, image enhancement techniques such as histogram equalization and Gaussian filtering are employed. These techniques enhance contrast, details, and local contrast, improving image visibility and quality.

In addition, a deep learning architecture called MIRNet is utilized to further enhance the images by capturing global and local features while preserving both details and textures. MIRNet utilizes invertible building blocks, residual connections, attention mechanisms, and a perceptual loss function to produce visually pleasing images with improved brightness, contrast, and details while reducing noise and artifacts associated with low-light conditions.

Transfer learning is employed to leverage pre-trained CNN models, specifically ResNet50 and VGG16, which have been trained on the ImageNet dataset. The pre-trained models' weights are utilized as an initialization point, and the final layers or some intermediate layers are modified or replaced to adapt to the ocular disease recognition task. This approach reduces the training time and data requirements while benefiting from the pre-trained models' learned representations and features.

To optimize the performance of the models, hyperparameter tuning is conducted using the Keras Tuner library. The library facilitates the search for optimal hyperparameters using techniques such as random search, hyperband, or Bayesian optimization. Area  
under ROC curve (or AUC) is the performance metric evaluated to further assess the model.

The ultimate goal of this study is to develop an accurate and efficient system for ocular disease recognition from fundus images. The findings and insights gained from this research can contribute to advancements in medical imaging and assist healthcare professionals in the early detection and treatment of ocular diseases, potentially improving patient outcomes and quality of life. 
 


#Dataset


Training Images (Not processed) -       https://drive.google.com/drive/folders/1JJfyuwoEiXNRkYM4kzw8-xihNFWVSIoD?usp=sharing
![image](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/9eb7709b-9aec-4bec-ab3d-a3cf29bb8863)


Cropped -                               https://drive.google.com/drive/folders/1fUIxa3pxVoCcsJJqxEgmCRN5zTMWLc1u?usp=sharing
![image](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/8f087e6e-fbf9-46d5-8c24-0e9628d296c7)

Resized -                               https://drive.google.com/drive/folders/1-JDS2owvl-Olf-dCFSdV56k3GXfcp25-?usp=sharing
![image](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/d802c6e8-b57b-41c3-a905-74576ddc0a35)

Image Preprocessing (CLAHE)
![image](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/1aaa0925-261d-40b5-8c58-74c5c3e19fb9)

Image Preprocessing (CLAHE + MSR ) -    https://drive.google.com/drive/folders/1-0U_xrU32HnsO0w3ZLdbJh2XCjEprEKK?usp=sharing
![image](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/e5f96cac-b2ae-4dac-b38b-3eb462225712)

Image Preprocessing (CLAHE + MIRNET ) - https://drive.google.com/drive/folders/1td4KD9f5B4NVgi3rky6yLIm-rrEKuqF9?usp=sharing
![image](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/597e15f1-c0d5-4f9d-811c-140e6015bda6)
