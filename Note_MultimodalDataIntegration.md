## Summary
To search for patients with non-small-cell lung cancer who are most likely to respond to immunotherapy, authors develop a **multi-modal risk prediction model** using deep learning techniques which incorporate the annotated **CT scan images**, digitized PD-1 and PD-L1 **immunohistochemistry slides** and **genomic sequencing data**, and outcomes of immune checkpoint inhibitor therapy.
  - **Data**  
    - To characterize the spatial distributions of CT signal intensities for each tumor, authors extract the quantitative image features from the segmented areas.
    - To characterize the spatial organization of PD-L1 immunoreactivity within the tumor, authors use PD-L1 immunohistochemistry slides.
    - **Limitation**: 1. insufficient sample size limit the generalizability of results. 2. small sample size also leads to data highly processed using expert knowledge, which hinders the model to learn the best features associated with immunotherapy reponse in a data-driven manner.
  - **Model**
    - The author's deep learning model stems from an article of **attention-based deep multiple instance learning**. 
    - The strength of this model: 1. it does not restrict the number of data types, enabling the model to be extended to other data modalities and to be applied to other cancers and diseases. 2. it considers the modalities for each patient with **different weights**, maximizating the predictive capacity of each type of data and thus improving the accuracy in predicting the response to immunotherapy (vs single biomarker). 3. even a patient has missing values in the CT scan or genomic sequence, the model can mask the missing data modality and compute a risk prediction. 4. the model can classify patients as immunotherapy responders or non-responders early after treatment.


## Terminology
- Dynamic attention with masking (DyAM)
- Permutation-tested area under the curve (AUC)
- Repeated subsampling-tested AUC
- Autocorrelation feature
- All gray level co-occurrence matrix (GLCM) features
- Multiple instance logistic regression (MILR)
- Tumor proportion score (TPS)