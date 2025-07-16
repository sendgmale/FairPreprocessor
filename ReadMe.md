<h1> [IEEE Intelligent Systems 2025] FairPreprocessor: Better Fairness via Addressing Imbalanced Data through Synthetic Data Generation and Mitigating Biased Labels </h1>



<h1> FairPreprocessor </h1>

This repository is for work **'FairPreprocessor: Better Fairness via Addressing Imbalanced Data through Synthetic Data Generation and Mitigating Biased Label'**.

********************************************************************************************************

**Analyze Parameter Sensitivity: Include an analysis of how parameter choices, such as crossover rate ranges, affect the results to enhance transparency and reproducibility.**

The document below analyzes how parameter sensitivity affects fairness and performance in various learners (LGR, RF, and DT) across different datasets.
https://docs.google.com/document/d/1dgXADXtxI4YEPrDR9AcpbpEkwyTjRVo5rl2deADYm_E/edit?tab=t.0

 ********************************************************************************************************

**Additional Ablation Studies on FairPreprocessor**

The below document contains the ablation experiments:
https://docs.google.com/document/d/12L6F8cI4oeqiYthCJTW40QuU6s56WG-MM43ZbhPmgAk/edit?usp=sharing 
 
 ********************************************************************************************************

FairPreprocessor is a preprocessing technique which addresses two causes of bias - 'imbalanced data' and 'biased labels'. We utilized nine popular publicly available datasets.
All datasets are available in the **Dataset** folder, except below, which were excluded due to size limitations.

They can be obtained from the below URLs.

MEPS15 - https://gitlab.liris.cnrs.fr/otouat/MEPS-HC/-/blob/main/h181.csv <br />
MEPS16 - https://gitlab.liris.cnrs.fr/otouat/MEPS-HC/-/blob/main/h192.csv

********************************************************************************************************

1. Adult Income dataset - http://archive.ics.uci.edu/ml/datasets/Adult
2. COMPAS - https://github.com/propublica/compas-analysis
3. German Credit - https://archive.ics.uci.edu/ml/datasets/Statlog+%28German+Credit+Data%29
4. Bank Marketing - https://archive.ics.uci.edu/ml/datasets/bank+marketing
5. Default Credit - https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients
6. Heart - https://archive.ics.uci.edu/ml/datasets/Heart+Disease
7. MEPS15 - https://meps.ahrq.gov/mepsweb/
8. MEPS16 - https://meps.ahrq.gov/mepsweb/
9. Student - https://archive.ics.uci.edu/ml/datasets/Student+Performance

********************************************************************************************************

**The replicate folder contains the codes to replicate our results. 
Replicate Package** -  https://drive.google.com/drive/folders/1Ls9fVj0Wf6Q_EsTbDmMwEEk0lDoimo1n?usp=sharing

**Steps to run the replicate files**

1. Download the package from this URL - https://drive.google.com/drive/folders/1Ls9fVj0Wf6Q_EsTbDmMwEEk0lDoimo1n?usp=sharing
2. Run the jupyter notebook correspond to the dataset.

*---------------------------------------------------------------------***

**FairPreprocesor: Achieving Fairness vias Handling Imbalanced Data through Synthetic Data**

We use 9 datasets, all of which are widely used in fairness research: Adult, COMPAS, German Credit, Default, Heart Disease, Bank Marketing, Student Performance, MEPS15 and MEPS16. We provide these data sets in the "datasets" folder. For MEPS15 and MEPS16, they can be loaded through python's aif360 package:

<code>from aif360.datasets import MEPSDataset19,MEPSDataset21</code>


The replicate folder contains the codes to replicate our results. 
The codes in the folder are named for the applicable scenarios. The Adult and COMPAS data sets include two protected attributes, so we divide them into two scenarios: Adult_sex (COMPAS_sex) and Adult_race (COMPAS_race).

<h1> Baselines </h1>
-----------------------------------------------------

**Fair-Smote: Proposed in the paper: Bias in Machine Learning Software: Why? How? What to Do?**
Fair-Smote is a pre-processing method that uses the modified SMOTE method to make the distribution of sensitive features in the data set consistent, and then deletes biased data through situation testing.
We use the code they provided in the code repository: https://github.com/joymallyac/Fair-SMOTE

**FairMask: Proposed in the paper: FairMask: Better Fairness via Model-Based Rebalancing of Protected Attributes**
Fairway is a hybrid algorithm that combines pre-processing and post-processing methods. 
We use the code they provided in the code repository: https://github.com/anonymous12138/biasmitigation 

**LTDD: Linear Regression Based Training Data Debugging**
LTDD is preprocessing algorithm that finds and removes the biased portion present in the features of the training data.
We use the code they provided in the code repository: https://github.com/fairnesstest/LTDD
 
**Reweighing: Data preprocessing techniques for classification without discrimination**
Reweighing is a pre-processing method that calculates a weight value for each data point based on the expected probability and the observed probability, to help the unprivileged class have a greater chance of obtaining favorable prediction results. 
We use the following python's AIF360 module to achieve it:

<code>from aif360.algorithms.preprocessing import Reweighing</code>

-----------------------------------------------------

All codes are run on the Ubuntu Operating System. 

--------------------------------


