# Ocular Disease Recognition
This project focuses on classifying ocular diseases from retinal fundus images using preprocessing techniques and deep learning models with transfer learning. It supports early diagnosis of conditions such as:
* Diabetic retinopathy
* Glaucoma
* Cataract
* Age-related macular degeneration (AMD)
* Hypertension-related changes
* Myopia
* Others
## Dataset
We use the ODIR dataset, which includes:
* Multilabel classification (patients may have more than one disease)
* Metadata (age, sex, left/right eye images)
* Raw fundus images of varying quality
The dataset and processed images are available via Google Drive:
- [Training Images (Raw)](https://drive.google.com/drive/folders/1JJfyuwoEiXNRkYM4kzw8-xihNFWVSIoD?usp=sharing)
- [Cropped Images](https://drive.google.com/drive/folders/1fUIxa3pxVoCcsJJqxEgmCRN5zTMWLc1u?usp=sharing)
- [Resized Images](https://drive.google.com/drive/folders/1-JDS2owvl-Olf-dCFSdV56k3GXfcp25-?usp=sharing)
- [CLAHE Enhanced](https://drive.google.com/drive/folders/1-0U_xrU32HnsO0w3ZLdbJh2XCjEprEKK?usp=sharing) 
- [CLAHE + MIRNet Enhanced](https://drive.google.com/drive/folders/1td4KD9f5B4NVgi3rky6yLIm-rrEKuqF9?usp=sharing)
## Example images:
| Preprocessing Step | Example Image                                                                                                                 |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Raw                | ![Raw](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/9eb7709b-9aec-4bec-ab3d-a3cf29bb8863)          |
| Cropped            | ![Cropped](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/8f087e6e-fbf9-46d5-8c24-0e9628d296c7)      |
| Resized            | ![Resized](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/d802c6e8-b57b-41c3-a905-74576ddc0a35)      |
| CLAHE              | ![CLAHE](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/1aaa0925-261d-40b5-8c58-74c5c3e19fb9)        |
| CLAHE + MIRNet     | ![CLAHE+MIRNet](https://github.com/SnehaDharne/OcularDiseaseRecognition/assets/55712542/597e15f1-c0d5-4f9d-811c-140e6015bda6) |
## Repository structure
| File                            | Purpose                                                                               |
| ------------------------------- | ------------------------------------------------------------------------------------- |
| `odir.csv`                      | Metadata and labels for the fundus images                                             |
| `odir_resize.ipynb`             | Resizing pipeline to normalize image dimensions                                       |
| `odir_crop_images.ipynb`        | Crops noisy borders and focuses on retinal regions                                    |
| `odir_enhancement.ipynb`        | Enhances fundus image quality using histogram equalization, CLAHE, Gaussian filtering |
| `hyp_resnet50_mirnet_msr.ipynb` | Experiments with MIRNet enhancement + ResNet50 model                                  |
| `hyp_vgg16_mirnet_msr.ipynb`    | MIRNet + VGG16 pipeline                                                               |
| `ODIR_balanced.ipynb`           | Class balancing using undersampling and training classifiers                          |
## Methods
### Image Preprocessing
* Resizing and cropping for spatial consistency
* Enhancement with:
  * CLAHE (Contrast Limited Adaptive Histogram Equalization)
  * Gaussian blurring
  * Histogram normalization
* Deep enhancement via **MIRNet** for denoising and contrast recovery. MIRNet utilizes invertible building blocks, residual connections, attention mechanisms, and a perceptual loss function to produce visually pleasing images with improved brightness, contrast, and details while reducing noise and artifacts.
### Classification Models
* ResNet50 and VGG16 with ImageNet weights
* Final classification head adapted for multilabel sigmoid outputs
* Training with binary cross-entropy loss and data augmentation
* Hyperparameter tuning using Keras Tuner (random search, hyperband, Bayesian optimization) with AUC as the primary metric
### Evaluation Metrics
* Per-class Precision, Recall, F1-score
* AUC-ROC across all labels
* Confusion matrices and class activation maps (CAMs)
## Results (Example)
| Model    | Preprocessing  | F1 (Macro) | AUC-ROC |
| -------- | -------------- | ---------- | ------- |
| VGG16    | MIRNet + CLAHE | 0.71       | 0.91    |
| ResNet50 | MIRNet + CLAHE | 0.74       | 0.93    |
MIRNet-enhanced images consistently outperformed raw image baselines.
## How to Run
1. Clone the repo:
```bash
git clone https://github.com/YOUR_USERNAME/OcularDiseaseRecognition.git
cd OcularDiseaseRecognition
```
2. Ensure your environment has:
```
tensorflow, keras, opencv-python, numpy, pandas, matplotlib, seaborn, scikit-learn, keras-tuner
```
3. Run notebooks in order:
   * `odir_resize.ipynb`
   * `odir_crop_images.ipynb`
   * `odir_enhancement.ipynb`
   * Model experiments (`hyp_*.ipynb`)
## Author
Sneha Dharne
MS in Computer Science (ML) – Stevens Institute of Technology
[LinkedIn](https://www.linkedin.com/in/snehadharne) • [GitHub](https://github.com/SnehaDharne)
## Credits
This project was developed as part of an academic thesis and presented at [event/institution name if needed].
### Additional Note
- The example images in the Dataset section are embedded using markdown images. They are hosted on GitHub (from the assets folder of the repo). The links in the table are direct links to the images.
