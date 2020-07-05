# Chest-X-ray-analysis
Analysis using ResNet50V2

<p> The dataset contains 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal). It was taken from kaggle, 'Chest X-Ray Images (Pneumonia)' Dataset. These Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care.For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnoses for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.</p>

<p> There are 1341 normal images and 3875 original images. Around 80% of the images have distinct dimensions. Hence all the images were resized to 256 x 256 and normalised before augmentation.
Since the x-ray images are in grayscale, a convolution layer is added after the input layer and the output matrix from this layer is fed to a pretrained ResNet50 network. A custom loss function is used to account for the imbalance in the dataset. Further, as accuracy cannot be used as a metric for imbalanced dataset, validation auc is calculated to find the best model. 

The validation AUC after 30 epochs were 0.9976
