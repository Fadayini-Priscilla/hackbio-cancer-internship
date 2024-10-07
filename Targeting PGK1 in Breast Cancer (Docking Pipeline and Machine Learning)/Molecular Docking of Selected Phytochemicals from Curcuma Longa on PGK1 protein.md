<!--StartFragment-->

# **Molecular docking of selected phytochemicals from _Curcuma longa_ on PGK1 protein**


## **Introduction**

Breast cancer is a common type of cancer affecting women worldwide and a leading cause of cancer-related deaths. The complexity and variability of breast cancer make it challenging to treat, especially in its more aggressive forms (Sung et al., 2021). The search for novel, more targeted therapies continues to grow due to the resistance to conventional treatments such as chemotherapy. One approach being explored is using natural compounds with anticancer properties, such as those in medicinal plants (Newman and Cragg, 2020).  Medicinal plants have long been a good source of drugs, for example, the Madagascar periwinkle which is used for treating cancer (Moudi et al., 2013). 

_Curcuma longa_, commonly known as turmeric, is a plant that has been used in traditional medicine for centuries particularly due to its bioactive compounds. It contains several active compounds called phytochemicals, curcumin being the most well-known for its antioxidant, anti-inflammatory, and anticancer properties (Gupta et al., 2011). Given their diverse biological activity, phytochemicals from _Curcuma longa_ are being investigated for their potential role in cancer therapy, including breast cancer (Gupta et al., 2012).

Phosphoglycerate Kinase 1 (PGK1) is critical in promoting tumour cell proliferation and inhibiting apoptosis. Its oncogenic role has been observed across various cancer types, including liver cancer, colon cancer, breast cancer, and glioblastoma multiforme (GBM). PGK1 is significantly upregulated in multiple tumour tissues compared to non-tumour tissues, reinforcing its association with cancer progression.

Key post-translational modifications (PTMs) like acetylation and O-GlcNAcylation regulate PGK1 activity, promoting cancer cell proliferation. For instance, acetylation at K323 enhances PGK1's enzymatic activity, contributing to liver cancer cell proliferation (Hu _et al_., 2017). PGK1 also influences the glycolytic pathway (Warburg effect), which supports the energy needs of rapidly proliferating cancer cells. Additionally, PGK1 promotes DNA replication and autophagy in cancer cells, which are essential for tumour survival and growth (Hu _et al_., 2017).

By docking phytochemicals from _Curcuma longa_ with PGK1, this study aims to evaluate their potential as inhibitors, providing insight into natural compounds that could lead to novel breast cancer treatments.


## **Materials and Methods**

## **Photochemical Library**

Phytochemicals were selected from _Curcuma longa_ (Iweala _et al_., 2023).

[Table 1](https://docs.google.com/document/d/1jWwa-9Eem9Mi3mbPwAvRumgTOEHXgQcI/edit?usp=sharing\&ouid=115010163280656693773\&rtpof=true\&sd=true): Phytochemical library from _Curcuma longa_ plant.


## **Molecular Docking**

PGK1 Protein structure (ID=4O33) was obtained from RCSB PDB and downloaded in the protein data bank (PDB) format.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcyaCYTdxuGYZrw0ksoa5dhKsYlke40jF__vWykHg-4zpXhjxMf2LTzaMQnAf64XFXDN845cJPrDEQHXNtV1GmsNFBMMbP0ApWK7jtqaNmlIpg-4P1JpQbQdnVfVeEdk6u154jDWQPpkJIJNsa1l4-TZUDs?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 1: PyMOL visualisation of 4O33 protein**

Pocket data describing the coordinates of all amino acids present was done from CASTp analysis of 4O33 protein. Information on amino acids present at the active site was obtained by visualising the active site and labelling the amino acids present. This was compared with their label on CASTp, and the corresponding coordinates were collated.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdYBiJsv7YEJv8D286mmaEQBBsSomAt93QBpgJEFWV-pRVvmkINl9PJxZyvzALOSQEqJ_4z1Uo4Oz2HKc2pb71FRn0zeQzzxY87py5Vszwooz-9VgK9Drv5GPdhogOppEJ-E_o0wx9itk2F7h1IhTg55K2i?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 2: PyMOL visualisation of 4O33 protein active site**

Average x, y, and z coordinates for pockets of amino acids in the active site were estimated and resulting coordinates were used as docking site, and to create a grid on AutoDock.

Structure Data File (SDF) of selected 53 phytochemicals from _Curcuma Longa_ was downloaded from PubChem.

Protein was loaded on Auto Dock Vina (version), water molecules, and heteroatoms were removed from the molecule, and macromolecule was modified to include all missing atoms. Polar hydrogens and Koleman charges were added to the molecule to properly distribute the charges across the protein molecule, the resulting molecule is saved in PDBQT format.

Using Ubuntu (version), energy minimization of SDF for all 53 phytochemical molecules is done using the following command in the location of the SD files. “obminimize”, then “obminimize -ff MMFF94 -n 1000 \*.sdf”. Then, they are converted to PDBQT format “obabel -isdf \*.sdf -opdbqt -O\*.pdbqt”.

A conformation text file was created to include the coordinates for molecular docking, which was obtained from the average values of all amino acids' x, y, and z coordinates in the active site of 4O33 protein. All ligand names were stored in a text file using the command “ls >ligand.txt” Perl Linux file was written to monitor molecular docking and molecular docking was performed using the following command on Ubuntu (v) “perl vina\_linux.pl”.

The results were collated in one text file from the command “tail -n11 \*.txt>results.txt”.


## **Results and Discussion**

Molecular docking results ([Table 2](https://docs.google.com/document/d/1wObgHVwe4-CQ5ly6EMqNriwnn3qRdHv6/edit?usp=sharing\&ouid=115010163280656693773\&rtpof=true\&sd=true)) show that 8 phytochemicals from the 53; α-Cedrene, β-Bisabolene, Curzerenone, Dihydrocurcumin, p-Cymene, Caffeic acid, α-Humulene, and δ-Cadinene have the best binding affinities, ranging from -7.7 to -8.3. This proves that these phytochemicals can inhibit cancer cell proliferation for breast cancer treatments.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe6SufWZ7xAaSawS5_5aKg41aa91i2PL90i0l_UW4-8ynYfmX8dkRkTu1s8s5PUllobKaeuFsOTBsKFiaJr88jgpKl-ASnv4FZTCWwho1DXK8Q62lBSl--2WbrxAbyjUQ7RvA_1CjRoPsUxOmAsVbAJAX7E?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 3: PyMOL visualisation of α-Cedrene docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf5vvOs0uxfOAmxv1LYNbubJTl1K0UzkstgoL7eTvYd-wg6sxC1ddaF7dHlh7vzu0IvoJ9SfgGwHbiAOD0cgKJ_mRTKXWcDcLFOO7F0kqOJqVMl6K_4Gjxs2wE4hoblIwhDLVDgirndHZFXVdJG-Ig7re0M?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 4: PyMOL visualisation of β-Bisabolene docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeV6_xvKVZQ0PprTc8JlkF0N61Q1KnKkxTGlDD-lwtaJ6j2kGGXpFFlHbS3zpU-Fi7WS42S_2Kf8inr-ZJRu28dkhjV_2uuJNZlN2Jzfcr84o9hn_f9phfvZtsRGDAqGSTbJY0Fb1RUpdY4KrAip3PBAeOH?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 5: PyMOL visualisation of Curzerenone docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd-ih7aLXSsXuVApPM6clWKy7yie8Dvpxc-AiMePoHIHr7vw9LLthEzjbTmA1Pc2EDiJUFdJ1_mWKN59tVKS7PPe0J-7y_ZYensByddYzTTadfdzMm8Xkv5RA3DRuYXUrDVsQWQ_SOPAxlIxS8Dtt3AnlwK?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 6: PyMOL visualisation of Dihydrocurcumin docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeRW3DtGkxyjP-gRwDqpjhLAc1f9YXtmfG9Y4YDAaNaJ-z9V6Gv-9w9B2xJQI6_6dRJUHyunHIECNXxRgkIn4K6OMqAr9pI9fW_4VIhL3wapFVVTZnrX4_6R8FOia0e3zjXfuDtGyKqIQzveUl1p79HTdYW?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 7: PyMOL visualisation of p-Cymene docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcu0wkkCzPtf-glEU8CTa1WbWAvaSvZgflgkxLnPZ0bl8pLbGAWEVtsJ6wF2WHQx40k-4Vn4SwGIZ6fBrtT8DDa2Nnm_JNnWA56yng8YEF3ryoTqC49UD0IgMkUq1I2og3gbZcBwG1vLqQxfqC556Zc4KCZ?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 8: PyMOL visualisation of Caffeic acid docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeOSYGSSRztbKbB-CeaAzlMaxOCUnmlNxxnaZnTSoTbt8Jp1mv17qdFhTERlr5YeEkmrjDbpidRP9zu-gKdmMN4qNOgCUIkZRAlU-HyPflGjo78u-IatyFaBvAGug60Cot3jSiEMM-dlHtPjEYA5l0LafWx?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 9: PyMOL visualisation of α-Humulene docked on 4O33 protein**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeyfZoOBv2kPjToaDCasvm50IFoa0iooObMFWaOIykQZrYCHnngXKasz8pdAdt4TK4GQb4SeGojaZ8x1kly7Eq9ICSCCqrzQJDSAwUXGVhvsTKjWMXuHfjkQQ3hu28GYjooUI8JC6zKSUxlxz2B5YhOloxx?key=ujy-ct2QySwOFKzXvUyudg)

**Figure 10: PyMOL visualisation of δ-Cadinene docked on 4O33 protein**

This study provides a pipeline for protein-ligand docking. PubChem and PyRx are open access thus this pipeline can be easily replicated which can be adjusted for a diverse scale of docking projects, contributing to the growing field of cancer drug discovery through natural products.


## **Conclusion**

The potential of phytochemicals derived from turmeric to target PGK1 has been shown in this study. Other experimental studies can be carried out to confirm the efficacy of the phytochemicals.

## **REFERENCES**

Sung, H., Ferlay, J., Siegel, R. L., Laversanne, M., Soerjomataram, I., Jemal, A., & Bray, F. (2021). Global Cancer Statistics 2020: GLOBOCAN Estimates of Incidence and Mortality Worldwide for 36 Cancers in 185 Countries. _CA: A Cancer Journal for Clinicians_, _71_(3), 209-249. <https://doi.org/10.3322/caac.21660>

David J. Newman and Gordon M. Cragg. Journal of Natural Products 2020 _83_ (3), 770-803. [https://doi.org/10.1021/acs.jnatprod.9b01285](https://doi.org/10.3322/caac.21660)

Moudi, M., Go, R., Yien, C. Y. S., & Nazre, Mohd. (2013). Vinca Alkaloids. _International Journal of Preventive Medicine_, 4(11), 1231–1235.

Gupta, S. C., Prasad, S., Kim, J. H., Patchva, S., Webb, L. J., Priyadarsini, I. K., & Aggarwal, B. B. (2011). Multitargeting by curcumin as revealed by molecular interaction studies. _Natural Product Reports_, _28_(12), 1937. <https://doi.org/10.1039/c1np00051a>

Gupta, S. C., Patchva, S., & Aggarwal, B. B. (2012). Therapeutic Roles of Curcumin: Lessons Learned from Clinical Trials. _The AAPS Journal_, _15_(1), 195-218. <https://doi.org/10.1208/s12248-012-9432-8>

Hu, H., Zhu, W., Qin, J., Chen, M., Gong, L., Li, L., Liu, X., Tao, Y., Yin, H., Zhou, H., Zhou, L., Ye, D., Ye, Q., & Gao, D. (2017). Acetylation of PGK1 promotes liver cancer cell proliferation and tumorigenesis. _Hepatology_, _65_(2), 515-528. <https://doi.org/10.1002/hep.28887> 

Iweala, E. J., Uche, M. E., Dike, E. D., Etumnu, L. R., Dokunmu, T. M., Oluwapelumi, A. E., ... & Ugbogu, E. A. (2023). Curcuma longa (Turmeric): Ethnomedicinal uses, phytochemistry, pharmacological activities and toxicity profiles—A review. _Pharmacological Research-Modern Chinese Medicine_, 6, 100222.

\


<!--EndFragment-->
