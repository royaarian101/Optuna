# Optuna
**Application of Optuna to find the optimal hyperparameters for transfer learning or fine tuning the pre-trained models**


# Introduction
This code was used to find best hyperparameters to classify MS and Normal cases using SLO images. However it can be used in any other application.

# Data Prepration
Applying subject-wise approach to split validation and train data

To prevent data leakage between train and validation datasets, a “subject-wise” approach was followed that involves putting all images belonging to each individual, regardless of its left-or-right orientation, in a single group.

Creating Dataset 

Create a dictionary for your dataset in which each key refers to one patient and the value of each key must be a nested-dictionary with own key and value. Keyes in nested dictionary indicate the number of images belonging to the patient and values are the corresponding numpy array of the images. Save this dictionary as a pickle file named (“subjects_slo_data.pkl”). However, the label dictionary contains keys and values, where the keys are the same as the keys in the image dictionary and the values are the patient’s label. Save this dictionary as a pickle file named (“labels_slo_data.pkl”) For example patient number one has 4 images with label = 1 and patient number two has 2 images with label = 0. Therefore, the corresponding dictionaries are as follow:

• images [0] is a dictionary with size (4):

• np.shape(images[0][0]) = (128 ×128 ×3)

• np.shape(images [0][1]) = (128 ×128 ×3)

• np.shape(images [0][2]) = (128 ×128 ×3)

• np.shape(images [0][3]) = (128 ×128 ×3)

 labels_train [0] = 1

• images [1] is a dictionary with size (2):

• np.shape(images [1][0]) = (128 ×128 ×3)

• np.shape(images [1][1]) = (128 ×128 ×3)

 labels_train [1] = 0

Remember to resize your images to (128 × 128 × 3) or change the input_shape in previous cell according to your desired size.

# Citing 
**Please ensure to include the following citations when utilizing any part of the code:**

[1] Arian, R., Aghababaei, A., Soltanipour, A., Khodabandeh, Z., Rakhshani, S., Iyer, S. B., Ashtari, F., Rabbani, H., & Kafieh, R. (2024). SLO-net: Enhancing multiple sclerosis diagnosis beyond optical coherence tomography using infrared reflectance scanning laser ophthalmoscopy images. Translational Vision Science & Technology, 13(7), 13. https://doi.org/10.1167/tvst.13.7.13

[2] Aghababaei A, Arian R, Soltanipour A, Ashtari F, Rabbani H, Kafieh R. Discrimination of Multiple Sclerosis using Scanning Laser Ophthalmoscopy Images with Autoencoder-Based Feature Extraction. Multiple Sclerosis and Related Disorders. 2024 Aug 1;88:105743–3.
