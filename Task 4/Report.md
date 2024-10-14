<!--StartFragment-->


# **REPRODUCING SCIENCE: FULL PIPELINE 2**


Authors (@slack): Akinkunmi Bamigboye (@akinn), Priscilla Fadayini (@Priscillaaa)


## **INTRODUCTION** ##

The study titled “Machine Learning Prediction of Cancer Cell Sensitivity to Drugs Based on Genomic and Chemical Properties” explores the integration of machine learning in cancer drug discovery. The researchers developed models to predict cancer cell line responses to therapies based on genomic features and the chemical properties of drugs. High-throughput screenings have revealed correlations between genetic alterations and drug sensitivity, motivating the use of computational methods to enhance predictive accuracy.

The machine learning models were trained to estimate the half-maximal inhibitory concentration (IC50) values, demonstrating strong performance with an R² of 0.72 in 8-fold cross-validation and 0.64 in independent tests. Notably, the models maintained predictive power for cell lines from different tissue types, achieving an R² of 0.61. This approach allows for estimating numerous IC50 values, significantly optimizing drug-cell screening designs.

The implications of this research extend beyond virtual screenings; it paves the way for testing thousands of compounds in silico, potentially uncovering new drug repositioning opportunities. Ultimately, these findings contribute to personalized medicine by aligning patients' genomic characteristics with drug sensitivity, thereby improving therapeutic outcomes in oncology.


## **ML METHODOLOGY** ##

The dataset, an XLSX file named “GDSC1\_fitted\_dose\_response\_27Oct23” was retrieved from the cancerrxgene.org website. The file was then imported on Google Colab and a dataframe was made of the information. The data was then cleaned and curated by removing missing values by dropping NaN, removing duplicate rows, and converting columns to appropriate data types.  The importance of choosing a cell line name with many entries for better performance and results from the model led to selecting the cell line name “SK-MEL-2” Erich had  402 entries. The data frame was then manipulated to show the four important columns: CELL\_LINE\_NAME, TCGA\_DESC, DRUG\_NAME, and LN\_IC50. SMILES of the drug names were generated from the PubChem database and further cleaned with the function .notna.The sorted data frame and the SMILES data frame were concatenated and descriptors were generated to yield the “df\_final” data frame. Test data is then generated from the whole data for model evaluation purposes.

To identify a model that would work well with our data, we trained the Pycaret model. Random Forest Regression provided the best performance in MSE, RMSE, and R<sup>2</sup>, balancing accuracy and efficiency as it minimized significant errors (MSE and RMSE). It prevents overfitting, lessens the effect of extreme values, and can be used with big datasets by using the ensemble of decision trees and the random selection of features and training ensuring that the model doesn't rely too heavily on any single feature. Random Forest Regression captures complex non-linear relationships between features and the target variable, hence uncovering interactions and patterns that may not be evident with simpler regression models.

The Random Forest Regression model was then evaluated using the test data set yielding the output: Mean Squared Error (MSE): 6.2311, Root Squared Error (RMSE):  2.4962, R-squared (R<sup>2</sup>): 0.1449,  Mean Absolute Error (MAE): 1.996.


## **RESULTS** ##

An R² of 0.1449 indicates that only about 14.49% of the variance in the target variable is explained by the model. This is relatively low, suggesting that the model is not capturing the underlying patterns in the data very well.

An MSE of 6.2311 suggests that there are some errors in the predictions, hence indicating some predictions are very different from the actual values.

The RMSE (Root Mean Square Error) value of 2.4962 indicates that, on average, the predictions made by your model deviate from the true values by approximately 2.5 units.

MAE represents the average absolute difference between predicted and actual values. Like MSE, lower values indicate better model performance. An MAE of 1.996 indicates that, on average, the predictions are off by about 1.996 units.

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/Actual%20vs%20Predicted%20IC50.png)

**Figure 1: Actual IC50 vs Predicted IC50**

Correlation Coefficient: 0.8547

The model is predicting IC50 rather well for many cases, as evidenced by the majority of data points falling along a diagonal line (predicted and actual values are near).

For **higher Actual IC50 values**, there is a tighter clustering along the diagonal, indicating better performance.

The model performs very well for moderate to high IC50 values but has trouble predicting low or negative IC50 values as the considerable departure from the diagonal line in those regions indicates.

A correlation coefficient of **0.8547** indicates a **positive and strong correlation** between the actual IC50 values and the predicted IC50 value. Since the coefficient is positive, it indicates that the relationship is direct; higher values of one variable are associated with higher values of the other. The correlation coefficient value is close to 1, indicating a reliable predictive relationship. A correlation coefficient of 0.8547 means that approximately 85.47% of the variability in one variable can be explained by the variability in the other, assuming a linear relationship.


## **COMPARISON** ##

Our model's R² value of 0.1449 indicates a low ability to explain variance in the data. Menden _et al_.'s model exhibits higher R² values, indicating a major amount of variance in medication response. The models by Menden _et al._ exhibit lower absolute errors, with RMSE values ranging from 0.83 to 0.89 and MSE values ranging from 0.6889 to 0.7921 (MSE = RMSE<sup>2</sup>), indicating reduced prediction error. Menden _et al._'s correlation coefficient was 0.85 for the majority of data and 0.82 for unknown cell lines but our correlation coefficient of 0.8547 is higher, indicating a stronger correlation than Menden _et al_.'s model.


## **CONCLUSION** ##

The model's performance is poor in predicting IC50 values, with high error values. Menden et al.'s model, using neural networks and random forests, performed significantly better, showing higher predictive power, strong correlations, lower errors, and better fit, as indicated by a high R². When compared to the findings in Menden et al., our model's predictive performance is noticeably worse, indicating that the model, features, or data size selection may be improved.


# **Molecular Docking of HDACs Subtypes with Selected Known Inhibitors and Phytochemicals from _Curcuma longa_**

## **INTRODUCTION** ##

Zinc-dependent histone deacetylases (HDACs), of three classes; class I, class II, and class IV consisting of HDAC 1, HDAC 2, HDAC 3, HDAC 4, HDAC 5, HDAC 6, HDAC 7, HDAC 8, HDAC 9, HDAC 10, and HDAC11 are enzymes that play a vital role in the epigenetic regulation of gene expression through the remodelling of chromatin (Shanmugam _et al_., 2022).

HDACs can regulate multiple cellular processes by deacetylating histones and numerous non-histone proteins involved in complex pathways within cancer cells, enabling them to escape immune detection and avoid cell death (Alseksek _et al._, 2021). Their activity in supporting the dysregulation of cancer cells as seen in ovarian cancers (Sudo _et al._, 2011) and poor survival in neuroblastoma (Rettig _et al._, 2015), make them good drug targets for cancer.

Employing histone deacetylase inhibitors (HDACi) are studied as a treatment for various cancers. In numerous tumour cell lines, HDACi increases the expression of the cell cycle gene p21, which disrupts cyclin/CDK complexes, resulting in cell cycle arrest and the inhibition of differentiation (Richon _et al._, 2000). HDACi also regulates the balance between pro-apoptotic and anti-apoptotic proteins, which causes tumour cell death (Kim & Bae, 2011).

## **METHODOLOGY** ##

## **MATERIALS & METHODS** ##

PDB of 9 HDACs; HDAC1 (5ICN), HDAC2 (7ZZS), HDAC3 (4A69), HDAC4 (2VQM), HDAC5 (5UWI), HDAC6 (5EDU), HDAC7 (3ZNR), and HDAC8 (2V5X) were retrieved from RCSB Protein Data Bank, while structures ofHDAC9 (Q9UKV0), HDAC10 (Q969S8), HDAC11 (Q96DB2) were modelled in AlphaFold3 using their fasta sequence from UniProt.

Inhibitors of the 11 HDAC subtypes and 50 phytochemicals from _Curcuma longa_ (Iweala _et al_., 2023) were retrieved from PubChem library and downloaded as Structure Data Files.

[Table 1](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/314d2adace7cd1d069e2e5d0a71539a1fa78f594/Task%204/HDAC%20Docking%20Ligands.md): Ligands for HDAC molecular docking.

Active sites of 11 HDACs were determined using CASTp. Energy minimisation of the 61 inhibitors was performed on PyRx, and both proteins and ligands were converted to PDBQT (Protein Data Bank, Partial Charge, and Atom Type) format using the same software. Ligands were docked on the HDACs using PyRx in triplicates to produce reliable results. The results of the binding affinities are shown in [Table 2](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/493f931affc95b4ae5214a149fa1d977a6ca4086/Task%204/Molecular%20Docking%20Binding%20Affinities.md).

## **RESULTS & DISCUSSION**

Molecular docking results of 11 HDACs subtypes are presented in [Table 2](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/493f931affc95b4ae5214a149fa1d977a6ca4086/Task%204/Molecular%20Docking%20Binding%20Affinities.md), and visualised as a heatmap in Figure 2. This analysis showed that the results were consistent, with a low range of standard deviation across results (0 - 1.1).

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/Heatmap%20for%20Binding%20Affinities%20of%20HDACs%20with%20Selected%20Inhibitors.png)


**Figure 2: Heatmap for Binding Affinities of HDACs with Selected Inhibitors**

5 ligands; Alloaromadendrene, ɑ-Selinene, β-Selinene, ẟ-Elemene, and TMP269 showed the highest binding affinities across the 11 HDAC subtypes. Allomandrendrene in HDAC3, HDAC5, and HDAC9,  ɑ-Selinene in HDAC4, β-Selinene in HDAC6, ẟ-Elemene in HDAC2 and HDAC8, and TMP269 in HDAC1, HDAC7, HDAC10, and HDAC11. Thus, these five ligands have significant inhibiting properties to these respective HDACs.

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/5icn_tmp269.png)

**Figure 3: PyMOL visualisation of HDAC1 (5ICN) with TMP269**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/7zzs_d-elemene.png)


**Figure 4: PyMOL visualization of HDAC2 (7ZZS) with ẟ-Elemene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/4a69_alloaromadendrene.png)


**Figure 5: PyMOL visualisation of HDAC3 (4A69) with Alloaromadendrene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/2vqm_a-selinene.png)


**Figure 6: PyMOL visualisation of HDAC4 (2VQM) with ɑ-Selinene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/5uwi_alloaromadendrene.png)


**Figure 7: PyMOL visualisation of HDAC5 (5UWI) with Alloaromadendrene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/5edu_b-selinene.png)


**Figure 8: PyMOL visualisation of HDAC6 (5EDU) with β-Selinene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/3znr_tmp269.png)


**Figure 9: PyMOL visualisation of HDAC7 (3ZNR) with TMP269**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/2v5x_d-Elemene.png)


**Figure 10: PyMOL visualisation of HDAC8 (2V5X) with ẟ-Elemene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/hdac9_alloaromadendrene.png)


**Figure 11: PyMOL visualisation of HDAC9 with Alloaromadendrene**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/hdac10_tmp269.png)


**Figure 12: PyMOL visualisation of HDAC10 with TMP269**

![](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/4da79b30729e11a88858e4fa6aaa2d9947a43632/Task%204/IMAGES/hdac11_tmp269.png)


**Figure 13: PyMOL visualisation of HDAC11 with TMP269**

TMP269 showed the highest binding affinity with HDAC11 (-7.3 ± 0)  compared to other ligands in this study which suggests it is a potential inhibitor for HDAC11. FT895 showed a good binding affinity of -6.40 ± 0 to HDAC11 which corresponds to the research by Baselious _et al_., indicating that FT895 interacts with HDAC11. 

## **CONCLUSION** ##

This study highlights the therapeutic potential of targeting HDACs with HDACi and phytochemicals from _Curcuma longa_, which can disrupt cancer cell survival mechanisms, such as immune evasion and inhibition of apoptosis. Through molecular docking simulations, TMP269 emerged as a promising inhibitor of HDAC11, demonstrating the highest binding affinity, and suggesting its potential as a targeted therapeutic agent for cancers driven by HDAC11 activity. These findings underscore the significance of HDAC inhibitors in cancer treatment and pave the way for further investigation into their clinical applications.

## **REFERENCES** ##

Menden, M. P., Iorio, F., Garnett, M., McDermott, U., Benes, C. H., Ballester, P. J., & Saez-Rodriguez, J. (2013). Machine Learning Prediction of Cancer Cell Sensitivity to Drugs Based on Genomic and Chemical Properties. _PLoS ONE_. 8(4): e61318.<https://doi.org/10.1371/journal.pone.0061318>

Shanmugam, G., Rakshit, S., & Sarkar, K. (2022). HDAC inhibitors: Targets for tumor therapy, immune modulation and lung diseases. _Translational Oncology_. 16, 101312. <https://doi.org/10.1016/j.tranon.2021.101312> 

Alseksek, R. K., Ramadan, W. S., & Saleh, E. (2021). The Role of HDACs in the Response of Cancer Cells to Cellular Stress and the Potential for Therapeutic Intervention. _International Journal of Molecular Sciences_. 23(15), 8141. <https://doi.org/10.3390/ijms23158141> 

Sudo, T., Mimori, K., Nishida, N., Kogo, R., Iwaya, T., Tanaka, F., Shibata, K., Fujita, H., Shirouzu, K.. & Mori, M. (2011). Histone deacetylase 1 expression in gastric cancer. _Oncology reports_. 26(4), 777-782.

Rettig, I., Koeneke, E., Trippel, F., Mueller, W. C., Burhenne, J., Fabian, J., Schober, A., Fernekorn, U., Von Deimling, A., Deubzer, H. E., Milde, T., Witt, O., & Oehme, I. (2015). Selective inhibition of HDAC8 decreases neuroblastoma growth in vitro and in vivo and enhances retinoic acid-mediated differentiation. _Cell Death & Disease_. 6(2), e1657. <https://doi.org/10.1038/cddis.2015.24> 

Kim, J., & Bae, C. (2011). Histone deacetylase inhibitors: Molecular mechanisms of action and clinical trials as anti-cancer drugs. _American Journal of Translational Research_. 3(2), 166-179. <https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3056563/> 

Richon, V. M., Sandhoff, T. W., Rifkind, R. A., & Marks, P. A. (2000). Histone deacetylase inhibitor selectively induces p21<sup>WAF1</sup> expression and gene-associated histone acetylation. _Proceedings of the National Academy of Sciences_. 97(18), 10014-10019. <https://doi.org/10.1073/pnas.180316197> 

Trott, O., Olson, A. J. (2010). AutoDock Vina: improving the speed and accuracy of docking with a new scoring function, efficient optimization and multithreading. _Journal of Computational Chemistry_. 31, 455-461.

Iweala, E. J., Uche, M. E., Dike, E. D., Etumnu, L. R., Dokunmu, T. M., Oluwapelumi, A. E., ... & Ugbogu, E. A. (2023). Curcuma longa (Turmeric): Ethnomedicinal uses, phytochemistry, pharmacological activities and toxicity profiles—A review. _Pharmacological Research-Modern Chinese Medicine_. 6, 100222.



<!--EndFragment-->
