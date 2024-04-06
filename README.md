# Predicting Porosity in Composite Materials Using Machine Learning, Ultrasound, and XCT

## Overview
This repository hosts the code and datasets for replicating the findings of the paper titled "Machine Learning-Based Data-Enhanced Ultrasonic Inspection of Porosity in Carbon Fiber Composites." Our study introduces a novel machine learning approach to estimate the void volume fraction (%v) in composite materials, utilizing ultrasonic testing and X-ray computed tomography (XCT).

## Contents
- **Dataframes**: Includes a CSV file detailing the attributes of each sample as described in the Materials section of the paper.
- **Notebooks**: Contains Jupyter notebooks with the code necessary to replicate our analysis and results. HTML versions are provided for easier viewing, not requiring a Jupyter-compatible IDE.
- **Results**: Contains text files with the analysis results.

## Requirements
The project utilizes the following libraries:
- `numpy`
- `scikit-learn`
- `pandas`
- `matplotlib`
- `napari` for nD-image visualization


## Most relevant results
The work introduces a methodology to estimate the void volume fraction (%v) in composite materials. The problem is framed as a machine learning supervised regression where attributes obtained from ultrasonic testing are used to estimate a ground truth void volume fraction measured by XCT. The most relevant resuls include:

1. A clear relation between void volume measured by XCT and attenuation of ultrasonic signal can be obtained by the proposed methodology. It depends on the kernel size to be applied on the XCT volume data.

<figure>
<img src="readmeResources\img_different_window.png" style="width: 650; height: auto;">
<figcaption> UT and XCT results for coupon 1. (a) Attenuation feature map with filter equivalent to $1x1mm^2$. Figure 4.12a) shows the XCT projection of the porosity for coupon 1. Images (b-f) represent the void volume fraction for window sizes of 1x1, 3x3, 5x5, 7x7, 9x9 $mm^2$. 
</figure>
<br>

2. The prediction of void volume is feasible. Due to the critic role in the safety of the Non-destructive Testing (NDT) industry, interpretability and visual tools for explainability of the results are developed.

<figure>
<center>
<img src="readmeResources\c4_RQ3.png" style="width: 650; height: auto;">
<figcaption> a) Prediction of void vol. b) Measured XCT void vol.  c) Absolute void volume error and d) Error images for the lineal model evaluated in the data set of coupon 1 and filter equal to $3x3 mm^2$. 
</figure>
<br>

3. A bilineal model was usually fit between void volume and attenuation. However, more complex models estimate better in unseen data. Several models that yield relevance weights were used. The use of neural networks is an ongoing future work.

<figure>
<center>
<img src="readmeResources\comp_pred_pors.png" style="width: 650; height: auto;">
<figcaption> Coupon 1 with filter size equal to $5x5 mm^2$.  a) Measured XCT void vol. Then void vol. prediction for each model: b) Lineal c) Multilineal c) Tree d) Random Forest models. This comparison shows how lineal predictions do not estimate as well as the multilineal model or the random forest for regions with very low or high values of void vol.. 
</figure>


## Other data
Original ultrasonic and XCT volume inspection data, as well as the code to create the datasets could be shared upon request in the email available on the paper. 
