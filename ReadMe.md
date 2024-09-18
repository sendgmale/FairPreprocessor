*---------------------------------------------------------------------***

**FairPreprocesor: Achieving Fairness vias Handling Imbalanced Data through Synthetic Data**

We use 9 datasets, all of which are widely used in fairness research: Adult, COMPAS, German Credit, Default, Heart Disease, Bank Marketing, Student Performance, MEPS15 and MEPS16. We provide these data sets in the "datasets" folder. For MEPS15 and MEPS16, they can be loaded through python's aif360 package:

<code>from aif360.datasets import MEPSDataset19,MEPSDataset21</code>


The replicate folder contains the codes to replicate our results. 
The codes in the folder are named for the applicable scenarios. The Adult and COMPAS data sets include two protected attributes, so we divide them into two scenarios: Adult_sex (COMPAS_sex) and Adult_race (COMPAS_race).

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
