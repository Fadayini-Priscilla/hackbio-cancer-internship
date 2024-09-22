# **Modelling and Visualisation of BRCA1 Protein in Apo, Agonist, and Antagonist Conformations.**

Authors (@slack): Bryan Muli (@brayo), Akinkunmi Bamigboye (@akinn), Abeeha Raza (@Abeeha97), Priscilla Fadayini (@Priscillaaa), Samuel Badekale (@SammyB)

**INTRODUCTION**

Breast cancer type 1 susceptibility (BRCA1) protein is a protein that in humans is encoded by the BRCA1 human tumour suppressor gene and is responsible for repairing DNA. Every human has two copies of the BRCA1 gene (one copy inherited from each parent) ( Hamel, 2007;  Duncan _et al_., 1998; Yoshida _et al.,_ 2004; Check, 2006)

BRCA1 is normally expressed in the cells of breast and other tissue, where it helps repair damaged DNA, or destroy cells if DNA cannot be repaired. It is involved in the repair of chromosomal damage with an important role in the error-free repair of DNA double-strand breaks. If BRCA1 is damaged by a BRCA mutation, damaged DNA is not repaired properly, and this increases the risk for breast cancer. BRCA1 has been described as "breast cancer susceptibility gene" and "breast cancer susceptibility protein". The predominant allele has a normal, tumour-suppressive function whereas high penetrance mutations in this gene cause a loss of tumour-suppressive function which correlates with an increased risk of breast cancer (Friedenson, 2007; O'Donovan _et al_., 2010) .

BRCA1 combines with other tumour suppressors, DNA damage sensors and signal transducers to form a large multi-subunit protein complex known as the BRCA1-associated genome surveillance complex (BASC). The BRCA1 protein associates with RNA polymerase II, and through the C-terminal domain, also interacts with histone deacetylase complexes. Thus, this protein plays a role in transcription, and DNA repair of double-strand DNA breaks ubiquitination, transcriptional regulation as well as other functions (Wang _et al_., 2000; Starita _et al.,_ 2003).

The three BRCA1 protein conformation structures we chose are:

- 1OQA: Representing the apo conformation, with no bound ligand.

- 1JNX: Representing the agonist conformation, with a single nickel (Ni) ligand.

- 21NG: Representing the antagonist conformation, with a mutation at the BRCT domain.

**Figure 1: 1JNX PDB structure**

**Figure 2: 1OQA PDB structure**

**Figure 3: 2ING PDB structure**

**DOMAINS**

The BRCA1 protein contains the following domains:

- RING (Really Interesting New Gene) domain: This consists of a RING finger and two flanking alpha helices encompassing amino acids 1-109 (exons 2-7). The RING finger coordinates two Zn<sup>2+</sup> atoms, stabilizing the RING structure, via seven conserved cysteine residues and one conserved histidine residue. The RING finger is a globular shape with a core three-strand β-sheet and a central helix. The surrounding helices align perpendicular to the ring finger. The RING finger is known to be responsible for BRCA1's E3-ubiquitin ligase activity (Hasan _et al_., 2014).

- BRCA1 serine clustered domain (SCD): A part of the BRCA1 SCD includes exons 11-13, which spans from amino acids 1280 to 1524. This part has a high concentration of potential phosphorylation sites and is phosphorylated by ATM/ATR kinases in vitro and in vivo. ATM and ATR kinases are activated when DNA is damaged. BRCA1 phosphorylation recruits the BRCA1 protein to double strand break sites. SCDs are frequent in ATM/ATR targets, which include many DNA damage response proteins (Hasan _et al_., 2014).

- Two BRCA1 C Terminus (BRCT) domain: BCRT domain occurs as a tandem repeat connected by a 22 amino acid linker in BRCA1 protein. Each BRCT repeat consists of three α-helices packed around a four strand β-sheet. The two BRCT repeats interact in a head-to-tail fashion through the interaction between α-helix 2 of BRCT1, and α-helices 1 and 3 of BRCT2 through mainly hydrophobic residues. The BRCT domain mediates phosphoprotein interactions between BRCA1 and proteins phosphorylated by ATM and ATR, two kinases activated by DNA damage. They could also mediate DNA binding and non-phosphoprotein interactions (Hasan _et al_., 2014).


## **BRCA1 BINDING AND ACTIVE SITES**

These contain: Valine-1654, Serine-1655, Glycine 1656, Leucine-1676, Threonine-1677, Asparagine-1678, Leucine 1679, Threonine 1700, Lysine 1702, Histidine 1805.

**Figure 4: 1JNX Nickel ligand and active site**

**Figure 5: 2ING ligands and active sites**


## **CANCER-RELATED MUTATIONS**

1. Mutations of the Cysteine residues known coordinate the Zn<sup>2+</sup> atoms have been identified as clinically significant, implying that they cause altered function and an increased risk of cancer. The RING motif is a conserved pattern consisting of seven cysteine and one histidine residues, forming two distinct Zn<sup>2+</sup> binding sites called site I and site II. Mutations of residues in site I affect the RING domain's folding. A more comprehensive analysis of site II residue alterations revealed altered structure using mass spectrometry and decreased Zn<sup>2+</sup> binding at site II. This study found that site II mutations had no effect on BRCA1 heterodimerization; however, a subsequent study by the same group found that several site I and site II mutations reduced not only ubiquitin ligase activity, but also co-immunoprecipitation of BRCA1 (Clark _et al_., 2012).

2. Mutation of these serine residues are seen clinically, and may affect localization of BRCA1 to sites of DNA damage and DNA damage response function (Clark _et al_., 2012).

3. Several studies have discovered mutations in the BRCT domain of BRCA1 in breast and/or ovarian cancers. Specifically, mutations of hydrophobic residues inside the BRCT domain's hydrophobic core impair BRCA1's capacity to identify phospholigands. This would imply that a mutation of residues necessary for substrate identification would impair BRCA1's capacity to function in the DNA damage repair pathway (Clark _et al_., 2012).


## **MODELLING TECHNIQUES**

We chose BRCA1 as our protein and ensured it is a protein present in the protein data bank. The 3D crystal protein structure was downloaded from RCSB (<https://www.rcsb.org/>) in pdb and fasta formats for further modelling. The SWISS and Alphafold were the modelling techniques employed.

**Homology Modelling using SWISS-MODEL**

Swiss-model (stylized as SWISS-MODEL) is a structural bioinformatics web-server dedicated to homology modelling of 3D protein structures. We performed homology modelling using SWISS MODEL, with the fasta format of protein gotten from RCSB PDB, based on the most accurate template, and downloaded the result in pdb format.

**Figure 6: 1JNX SWISS model**

**Figure 7: 1OQA SWISS model**

**Figure 8: 2ING SWISS model**

\


**Table 1: SWISS model features of BRCA1 conformation**

|                               |              |                  |                |             |                                        |                 |
| :---------------------------: | ------------ | ---------------- | -------------- | ----------- | :------------------------------------: | :-------------: |
|         **Structure**         | **Template** | **Identity (%)** | **Similarity** | **Ligands** |               **Method**               | **Oligo state** |
|     1OQA            ( Apo)    | 1t15.1.A     | 100              | 0.63           |        -    | &#xA;&#xA;&#xA;X-ray, &#xA;&#xA;1.85 Å |     monomer     |
|  1JNX             ( Agonist)  | 1t15.1.A     | 100              | 0.62           |        -    |  &#xA;&#xA;&#xA;X-ray,&#xA;&#xA;1.85 Å |     monomer     |
| 2ING            ( Antagonist) | 1t15.1.A     | 98.59            | 0.62           |        -    | &#xA;&#xA;&#xA;X-ray, &#xA;&#xA;1.85 Å |     monomer     |

**AlphaFold Modeling**

AlphaFold is Google DeepMind's contribution to the long-standing problem of protein structure prediction. It predicts the 3D structures of proteins with a high degree of accuracy and is now widely used by researchers. We performed AlphaFold modelling on AlphaFold server with the protein fasta file obtained from the RCSB, and saved the result in zip format.

The **predicted IDDT (Distance Difference Test) per position** indicates the confidence of AlphaFold’s predictions for each residue. Higher values (closer to 100) represent more confident predictions, and lower values indicate less confident predictions. The AlphaFold models were confident about the main structure, but showed uncertainty in few flexible regions

The **contact maps** display predicted residue-residue contacts in the protein structure for each rank (1-5).Red areas represent low proximity (no close contact), while blue indicates regions where residues are likely in close spatial proximity.

The **sequence coverage** shows the region with high sequence identity and coverage (the green and blue colours indicating good coverage)

**Figure 9: 1JNX AlphaFold model**

**Figure 10: 1JNX AlphaFold plots**

**Figure 11: 1OQA AlphaFold model**

**Figure 12: 1OQA AlphaFold plots**

**Figure 13: 2ING AlphaFold model** 

****

**Figure 14: 2ING AlphaFold plots**

**Similarities between both modelling techniques**

- Both methods predict a similar overall fold for BRCA1 protein conformations.

- Both methods agree on the secondary structure elements (alpha helices and beta sheets).

- Both methods predict a similar organization of the domains.

- Both methods models did not include ligands present in each conformation.


## **PROTEIN VISUALIZATION** 

With the help of PyMol, the proteins were visualized successfully.

**Evaluating both modelling techniques as compared to the crystal structures on the PDB**

(using align and RMSD measurements on pymol)

We calculated the RMSD value on pymol with the help of this command:

_align molecule1, molecule2, cycles=0, transform=0_

**Table 2: RSMD results of PyMol visualization**

|                               |                                             |                                         |
| :---------------------------: | :-----------------------------------------: | --------------------------------------- |
|      **Database protein**     | **RSMD of Alphafold model & PDB alignment** | **RSMD of SWISS model & PDB alignment** |
|     1OQA            ( Apo)    |                    0.943                    | 1.172                                   |
|  1JNX             ( Agonist)  |                    0.486                    | 0.364                                   |
| 2ING            ( Antagonist) |                    0.727                    | 0.741                                   |

\


****

**Figure 15: Alignment of 1JNX SWISS model with its PDB crystal structure**

**Figure 16: Alignment of 1OQA SWISS model with its PDB crystal structure**

**Figure 17: Alignment of 2ING SWISS model with its PDB crystal structure**

**Figure 18: Alignment of 1JNX AlphaFold model with its PDB crystal structure**

**Figure 19: Alignment of 1OQA AlphaFold model with its PDB crystal structure**

**Figure 20: Alignment of 2ING AlphaFold model with its PDB crystal structure**


## **CONCLUSION**

The more accurate modelling technique for our protein is the AlphaFold modelling as it gives overall low RMSD values showing great similarity to the PDB’s crystal structure as compared to SWISS modelling.

From **_Table 2_**, the SWISS model generates the agonist conformation as it shows lesser RMSD value for this conformation while the AlphaFold model generates the antagonist conformation.


## **REFERENCES**

Hamel, P. J. (2007). BRCA1 and BRCA2: No Longer the Only Troublesome Genes Out There. _Health Central_. Retrieved 2010-07-02.

Duncan, J. A., Reeves, J. R., & Cooke, T. G. (1998). BRCA1 and BRCA2 proteins: roles in health and disease. _Molecular Pathology_. 51(5), 237–47. [doi]:[10.1136/mp.51.5.237](https://doi.org/10.1136%2Fmp.51.5.237).

Yoshida, K., & Miki, Y. (2004). Role of BRCA1 and BRCA2 as regulators of DNA repair, transcription, and cell cycle in response to DNA damage. _Cancer Science_. 95(11), 866–71. [doi]:[10.1111/j.1349-7006.2004.tb02195.](https://doi.org/10.1111%2Fj.1349-7006.2004.tb02195.x)

Check, W. (2006). BRCA: What we know now. _College of American Pathologists._ Retrieved 2010-08-23.

Friedenson, B. (2007). The BRCA1/2 pathway prevents hematologic cancers in addition to breast and ovarian cancers. _BMC Cancer_. 7, 152–162. [doi]:[10.1186/1471-2407-7-152](https://doi.org/10.1186%2F1471-2407-7-152)

O'Donovan, P. J., & Livingston, D.M. (2010). BRCA1 and BRCA2: breast/ovarian cancer susceptibility gene products and participants in DNA double-strand break repair. _Carcinogenesis_. 31 (6): 961–7. [doi]:[10.1093/carcin/bgq069](https://doi.org/10.1093%2Fcarcin%2Fbgq069)

Wang, Y., Cortez, D., Yazdi, P., Neff, N., Elledge, S. J., & Qin, J. (2000). BASC, a super complex of BRCA1-associated proteins involved in the recognition and repair of aberrant DNA structures. _Genes & Development_. 14 (8): 927–39. [doi]:[10.1101/gad.14.8.927](https://doi.org/10.1101%2Fgad.14.8.927)

Starita, L. M., Parvin, J. D. (2003). The multiple nuclear functions of BRCA1: transcription, ubiquitination and DNA repair"m. _Current Opinion in Cell Biology_. 15 (3): 345–350. [doi]:[10.1016/S0955-0674(03)00042-5](https://doi.org/10.1016%2FS0955-0674%2803%2900042-5).

Clark,  S. L., Rodriguez, A. M., Snyder, R. R.(https://pubmed.ncbi.nlm.nih.gov/?term=Snyder%20RR%5BAuthor%5D), Hankins, D. V.,  & Boehning, D. (2012). Structure-Function of the Tumour Suppressor BRCA1. _Computational and Structural Biotechnology Journal_. doi:[10.5936/csbj.201204005](https://doi.org/10.5936%2Fcsbj.201204005)

\
\
![](blob:https://gdoc2md.com/08355c7a-9237-473e-9159-e142264cee03)![](blob:https://gdoc2md.com/f1c2b9ba-8728-4623-bbe2-d03d8ffc8cf5)![](blob:https://gdoc2md.com/cd676efc-4924-4643-82f9-fab3ee04ac31)![](blob:https://gdoc2md.com/cf4c4f1f-b325-4bd1-af1e-8edc63a0c416)![](blob:https://gdoc2md.com/ea625351-cf21-470c-98f9-aeb49a141834)![](blob:https://gdoc2md.com/e758b0e0-63aa-4a2e-b2f3-6b0b2e0a0be4)![](blob:https://gdoc2md.com/198c925b-13f7-4381-b06f-f697ea927696)![](blob:https://gdoc2md.com/4ff70831-f972-4fc6-bd6d-666c2b93b1b1)![](blob:https://gdoc2md.com/ce60428d-bdbb-4987-b0cf-1b6806d638c1)![](blob:https://gdoc2md.com/ee1da19f-d3f6-4198-8f09-b1010b22b967)![](blob:https://gdoc2md.com/087918a1-bde7-4614-8d6e-c9b435b98a2a)![](blob:https://gdoc2md.com/3b47be43-f5d7-454f-ac4a-d991f839a467)![](blob:https://gdoc2md.com/7099c1b1-c8ab-4ddf-bb03-8f844ccf8220)![](blob:https://gdoc2md.com/c666b2f7-d7e7-4dad-b3c1-60bd69054da6)![](blob:https://gdoc2md.com/90fd2192-e510-42d4-a85d-d24662134030)![](blob:https://gdoc2md.com/4c8b6615-fe11-4ce7-b1fe-36df2098f0c6)![](blob:https://gdoc2md.com/22984210-81f0-42d4-9433-7edeea0d6a48)![](blob:https://gdoc2md.com/c2a4b14c-f1ab-458a-bc4c-fe30857b00dd)![](blob:https://gdoc2md.com/a0336353-d133-4818-8279-55c0d612fad0)![](blob:https://gdoc2md.com/f06e36da-27fe-48fa-9fc6-3ce396f48088)
