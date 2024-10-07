<!--StartFragment-->


# **Using Machine Learning Model to Predict Bioactive Compounds** 

## **Introduction** 

The PGK1 gene encodes a glycolytic enzyme that converts 1,3-diphosphoglycerate to 3-phosphoglycerate and may also be a cofactor for polymerase alpha. The protein is secreted by tumour cells for angiogenesis, reducing disulfide bonds in plasmin, leading to the release of angiostatin, a tumour blood vessel inhibitor. The encoded protein is identified as a moonlighting protein due to its distinct functions.

Terazosin, a potential drug known to target PGK1 protein of SMILES(COC1=C(C=C2C(=C1)C(=NC(=N2)N3CCN(CC3)C(=O)C4CCCO4)N)OC), specifically inhibit PGK1 in vitro by activating PGK1 to produce more ATP to activate HSP90, thus protecting organ damage from multi-stress challenges

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfc0G6BLP5ibGAVGx-1h0c0yOLrhamMKn6qdzeWmJZ88fuzH8oJWJ0h37vOflKrB-UOLTqP20SMKYDxM6B1SYU7j1pOdb2h2xZhG_UeZRcrJ10kC_skWHxR4FU6Wkt9M6NKObl-eDHM2Kma59kzBJmKCByma8yvdXX7FPDZSA?key=9OHSq5zjQKYauXezibhhwQ)

**Figure 11: Terazosin structure**

**Methodology**

ChEMBL bioactivity data for PGK1 was retrieved, IC50 values were converted to pIC50, and molecular descriptors generated using RDKit. A Random Forest Regressor was trained, evaluated using MSE and R-squared, and cross-validated using KFold. Predictions for the docked compounds and a ligand known to inhibit PGK1 (Terazosin) were made using the trained model. The Google Colab notebook can be accessed ([here](https://github.com/Fadayini-Priscilla/hackbio-cancer-internship/blob/0e39c406c77d21650ff205831520d2fef3a5f9c3/Targeting%20PGK1%20in%20Breast%20Cancer%20(Docking%20Pipeline%20and%20Machine%20Learning)/Machine%20Learning%20Code%20for%20PGK1.ipynb)) for further details.

**Results**

The Random Forest model showed moderate performance and generalization ability, with a Root Mean Squared Error (RMSE) of 0.79, Mean Absolute Error (MAE) of 0.60, and an R-squared value of 0.49. Cross-validation using KFold resulted in MSE scores ranging from 0.62 to 0.69, with an average MSE of 0.65. This model predicted the pIC50 values for 50 docked ligands and Terazosin, aiding in potential bioactive compound identification against the target protein, PGK1. The predicted pIC50’s can be accessed [here](https://github.com/RxRuqayyah/Hackbio-Internship/blob/main/Targeting%20ELGN1%20in%20cervical%20cancer%20\(Docking%20Pipeline%20and%20Machine%20Learning\)/Predicted%20IC50.md).

**Discussion**

The bioactivity of PGK1 is predicted using key molecular descriptors such as Molecular Weight, log P, and Hydrogen Bond Acceptors. A balanced log P ensures effective binding, an adequate MW aids penetration, and hydrogen bond acceptors facilitate interaction with major residues. The Random Forest model's performance is below average, explaining 49% of the variance in pIC50 values. Moderate MSE scores suggest the model's utility in virtual screening but highlight potential limitations due to dataset size and feature complexity.

**Conclusion**

Machine learning predicts bioactivity against PGK1 with moderate accuracy, but improvements in dataset expansion and feature enhancement are needed for better drug discovery results.

\


<!--EndFragment-->
