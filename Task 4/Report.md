<!--StartFragment-->


# **REPRODUCING SCIENCE: FULL PIPELINE 2**


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

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd9T39WAsbF5E8T6SsUmTiPk6GaBc2EEKRrDACDR4vFHljDs2cj-6Gq720jqEaIpoKzB0_A5FUQBu_SV54QfjZzPS9-lP54KuSBEzr2xZD93GiUeVrspwdoTEZpE2Iod0KbJIjKMzEc-OJU6UyuRAEsKIS_?key=VnO3vB75pdrrGTifxiAKrg)


Figure 1: Actual IC50 vs Predicted IC50

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

[Table 1](https://docs.google.com/document/d/1DZwPM9vvZoMjyXv7rJhcEre7jh_1Q33i/edit): Ligands for HDAC molecular docking.

Active sites of 11 HDACs were determined using CASTp. Energy minimisation of the 61 inhibitors was performed on PyRx, and both proteins and ligands were converted to PDBQT (Protein Data Bank, Partial Charge, and Atom Type) format using the same software. Ligands were docked on the HDACs using PyRx in triplicates to produce reliable results. The results of the binding affinities are shown in [table 2](https://docs.google.com/document/d/1K2KLkKbRpcXamicbV9uTFnKmcXr8gmNtYA_--2R8krQ/edit?usp=sharing).

## **RESULTS & DISCUSSION**

Molecular docking results of 11 HDACs subtypes are presented in [Table 2](https://docs.google.com/document/d/1K2KLkKbRpcXamicbV9uTFnKmcXr8gmNtYA_--2R8krQ/edit?usp=sharing), and visualised as a heatmap in Figure 1. This analysis showed that the results were consistent, with a low range of standard deviation across results (0 - 1.1).

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf3OFyzS3OoRRDsql2DcKW3Gkiak7jwF8Zph1nPxwcXvGQxWVaBxvW0oqlky7yC84xaL6oXL1hRAQt0iXogbXmbIBxysdCkqSHPZSyW_5Ov8tUVVOTHnKqXfM2KrdwL1S9Ca7HPvdg82bt6a1kyulf0KQeT?key=VnO3vB75pdrrGTifxiAKrg)


Figure 2: Heatmap for Binding Affinities of HDACs with Selected Inhibitors

5 ligands; Alloaromadendrene, ɑ-Selinene, β-Selinene, ẟ-Elemene, and TMP269 showed the highest binding affinities across the 11 HDAC subtypes. Allomandrendrene in HDAC3, HDAC5, and HDAC9,  ɑ-Selinene in HDAC4, β-Selinene in HDAC6, ẟ-Elemene in HDAC2 and HDAC8, and TMP269 in HDAC1, HDAC7, HDAC10, and HDAC11. Thus, these five ligands have significant inhibiting properties to these respective HDACs.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe_jN7ty4XSZr27DVfyxKJxCG2b-mJeap2D4XeGqPF_GwgHgclwIzwWmI0dehIPGwTr4t-pFnwNUJagdE7lCoNuSvJlcvjaCPVJeuSNixHwj5GG6yK7m1Wo29wX_EOWkjzr_ZRUDh5UsHeVL6CnUt5smYBY?key=VnO3vB75pdrrGTifxiAKrg)


Figure 3: PyMOL visualisation of HDAC1 (5ICN) with TMP269.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXewAJ3N7UoqKlHdP3Hk9EEkPmrZWJ9mbajJw4r8AJCmTqjsN6ykEGrBUwhEyZySLLPD-3X3IMHZYuetV0gnLmI8e-KZX_e0eKrYLye0aRHsIJpPZD7YTV_YbSraVCt8qLa6OeYT89dumoDrGSff5OAUwSBf?key=VnO3vB75pdrrGTifxiAKrg)


Figure 4: PyMOL visualization of HDAC2 (7ZZS) with ẟ-Elemene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcUSIwxZl4jrwNzF30n8gIG9DrmvjlgLyhk_w7XIRVp-wAFzrTjPZpGW_ke3C_0PWhOyLsqX5te1nTB2U3F-kZUW-24RRkUic2l8gqsh0q0ColhFoG1Q_IsYgGp1tBUt9BUz2_yGOjvPBvivmp5tviGZeFu?key=VnO3vB75pdrrGTifxiAKrg)


Figure 5: PyMOL visualisation of HDAC3 (4A69) with Alloaromadendrene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf4eBT4In57DfwX0i-L76Fjw8jv8gas6Nl4ueKnIwqe8wkwHWsn19QAmGk1V0DxW5GpQQDGUM04i6M6CXW_wtWIygfYwiD77iqlSDEy177eKNt4-CRAr20Q3fRwYNf0xhjBqC23ePA6Q2guQydNTXiwY-g?key=VnO3vB75pdrrGTifxiAKrg)


Figure 6: PyMOL visualisation of HDAC4 (2VQM) with ɑ-Selinene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfNDDsrbKXsLtWoRZRwdntcnyeCU2zmsg7aOY4zoQpd95HE8LXl_MwUwcJNL7SOABNx9SC5XLEO2QUypAZhUGgv-4KPNuzViXnqdcjyiI6zwAD3wfmMSk4VpW0IrIrJHRw2cKKt2wcvFrfSCr4ymTjtzR8s?key=VnO3vB75pdrrGTifxiAKrg)


Figure 7: PyMOL visualisation of HDAC5 (5UWI) with Alloaromadendrene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcOFhz5xai6FrH73DftbNNJ16BzWNkFSYuw7ppOy5p9D9TlYH4BUhlFNlF3ys0N_pYxbaMAwd7NbNa_zJ0A3g49G9tUu21mSjsUpHidB5fLIsWmJfvi4lie0j5e1tcrWE66DmfMwdL7yxW-o2MQGwt2Amkt?key=VnO3vB75pdrrGTifxiAKrg)


Figure 8: PyMOL visualisation of HDAC6 (5EDU) with β-Selinene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcOW8Xq7W3aaQq5RqGPq03scXAxXPs1Jrm3t-nrHDu7VaepQzkerXV77fXgljNBXB-FH6Y-8imUUXUTGYGu8eJGOw1gH5Tir8ptxDBy27xj1Mu1ggTtFHXoLEy18nAEnkRZAA8w1S5j3mhfFrG9av8c1cva?key=VnO3vB75pdrrGTifxiAKrg)


Figure 9: PyMOL visualisation of HDAC7 (3ZNR) with TMP269.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfaCeOsVUiUWh5CGshh861fkRjxaoVfTzVqm8Ko97MBefciIGWbdteR0wzVwO4H-HHFqgR_ve507LGqD0mNVTlsT_8HB_ng_mXYDZElfWzxDkBkeMC5qXgPyeRqR5cU5U17U1YhvMArjZs3w1pMlqYrN9qg?key=VnO3vB75pdrrGTifxiAKrg)


Figure 10: PyMOL visualisation of HDAC8 (2V5X) with ẟ-Elemene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc4lKeJKj7v1Yo1qbB-RL7E2X62kxYysv0ok2cj9OLpshoClykm2DDiciAGTzyqxuedFqEfOMO9zgk8vuOAE7aA0ZsnfjaPKn1J2kjE3uM6w5JTg0CHw3sSE0XJnTGauLQQcpWOyCYNSH7kkUdXodMoNcY?key=VnO3vB75pdrrGTifxiAKrg)


Figure 11: PyMOL visualisation of HDAC9 with Alloaromadendrene.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfsOLVXq1w79OrpzU_K31aI1hfKYy6iJ5Y6-DICI3Drvs5V_kVqEOtjBJRZqgwQmYuQmIOYaFWXCNLtAJ2vX-vJOWW7kpdiPcrcs99kNA3bMNKokz4XDK7zPsTOJPjLHjfC6sKvLmrxJAxaaqOSB1gTHRB8?key=VnO3vB75pdrrGTifxiAKrg)


Figure 12: PyMOL visualisation of HDAC10 with TMP269.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcSGfaQVprDNPYSE-Zajo5EyMn9k-hYQo8W9q4QfiWrd9sneY8yrn1tkwR9WrchFg7H5u3v-dp8ijsXLX7Qv6aS6nDqZNApJbEyMq0wjR_j8ZukxfeLsyviFJ28WvET8TqNpYt1EfxuBlz5UdkjNUJaoh8?key=VnO3vB75pdrrGTifxiAKrg)


Figure 13: PyMOL visualisation of HDAC11 with TMP269.

TMP269 showed the highest binding affinity with HDAC11 (-7.3 ± 0)  compared to other ligands in this study which suggests it is a potential inhibitor for HDAC11. FT895 showed a good binding affinity of -6.40 ± 0 to HDAC11 which corresponds to the research by Baselious _et al_., indicating that FT895 interacts with HDAC11. 

## **CONCLUSION** ##

This study highlights the therapeutic potential of targeting HDACs with HDACi and phytochemicals from _Curcuma longa_, which can disrupt cancer cell survival mechanisms, such as immune evasion and inhibition of apoptosis. Through molecular docking simulations, TMP269 emerged as a promising inhibitor of HDAC11, demonstrating the highest binding affinity, and suggesting its potential as a targeted therapeutic agent for cancers driven by HDAC11 activity. These findings underscore the significance of HDAC inhibitors in cancer treatment and pave the way for further investigation into their clinical applications.

## **REFERENCES** ##

\[Menden MP, Iorio F, Garnett M, McDermott U, Benes CH, Ballester PJ,\
et al. (2013) Machine Learning Prediction of Cancer Cell Sensitivity to Drugs Based on Genomic and Chemical Properties. PLoS ONE 8(4): e61318.<https://doi.org/10.1371/journal.pone.0061318>

Shanmugam, G., Rakshit, S., & Sarkar, K. (2022). HDAC inhibitors: Targets for tumor therapy, immune modulation and lung diseases. _Translational Oncology_, _16_, 101312. <https://doi.org/10.1016/j.tranon.2021.101312> 

Alseksek, R. K., Ramadan, W. S., & Saleh, E. (2021). The Role of HDACs in the Response of Cancer Cells to Cellular Stress and the Potential for Therapeutic Intervention. _International Journal of Molecular Sciences_, _23_(15), 8141. <https://doi.org/10.3390/ijms23158141> 

Sudo, T., Mimori, K., Nishida, N., Kogo, R., Iwaya, T., Tanaka, F., Shibata, K., Fujita, H., Shirouzu, K.. & Mori, M. (2011). Histone deacetylase 1 expression in gastric cancer. Oncology reports, 26(4), 777-782.

Rettig, I., Koeneke, E., Trippel, F., Mueller, W. C., Burhenne, J., Fabian, J., Schober, A., Fernekorn, U., Von Deimling, A., Deubzer, H. E., Milde, T., Witt, O., & Oehme, I. (2015). Selective inhibition of HDAC8 decreases neuroblastoma growth in vitro and in vivo and enhances retinoic acid-mediated differentiation. _Cell Death & Disease_, _6_(2), e1657. <https://doi.org/10.1038/cddis.2015.24> 

Kim, J., & Bae, C. (2011). Histone deacetylase inhibitors: Molecular mechanisms of action and clinical trials as anti-cancer drugs. _American Journal of Translational Research_, _3_(2), 166-179. <https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3056563/> 

Richon, V. M., Sandhoff, T. W., Rifkind, R. A., & Marks, P. A. (2000). Histone deacetylase inhibitor selectively induces p21<sup>WAF1</sup> expression and gene-associated histone acetylation. _Proceedings of the National Academy of Sciences_, _97_(18), 10014-10019. <https://doi.org/10.1073/pnas.180316197> 

Trott, O., Olson, A. J. (2010). AutoDock Vina: improving the speed and accuracy of docking with a new scoring function, efficient optimization and multithreading. _Journal of Computational Chemistry,_ 31, 455-461.

Iweala, E. J., Uche, M. E., Dike, E. D., Etumnu, L. R., Dokunmu, T. M., Oluwapelumi, A. E., ... & Ugbogu, E. A. (2023). Curcuma longa (Turmeric): Ethnomedicinal uses, phytochemistry, pharmacological activities and toxicity profiles—A review. _Pharmacological Research-Modern Chinese Medicine_, 6, 100222.



<!--EndFragment-->
