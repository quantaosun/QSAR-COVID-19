# QSAR fro COVID-19
70% of the notebook coding are borrowed from https://github.com/dataprofessor as claimed inside some of the notebooks, with modification
30% of the notebook is written from scratch.
# Pre-conditions: Jupyter notebook
Windows, Mac or Linux erither is fine as long as you have a jupyter notebook installed.
# What is it do
This repository is to build a QSAR model based on molecular descriptors and bioactivities, with the help of machine learning model random forest regression, to build a QSAR model either based on public chembl bioactivity or your local bioactivity for SARS-COV-2, or if you could change the target, for any other target.

# 1. Starting from public data
This senario is not discussed for the moment, as it is easier to handle compared to the second.
# How to use it
run public.ipynb, 2,3,4,5 in sequence to build a QSAR, then run 3,5 of another repository https://github.com/quantaosun/QSAR-Chembl-Prediction to predict unknow molecules.

# 2. Starting from your local data
# How to use it
run local.ipynb, 2,3,4,5 in sequence to build a QSAR, then run 3,5 of another repository https://github.com/quantaosun/QSAR-Chembl-Prediction to predict unknow molecules.

Before you could run a local version, do the following as preconditions,

1. Prepare a text file that contains all the molecules' smiles string, you can obtain it from ChemDraw or any other means you prefer, note that there are various variants of smile, what I used here is the conventional one. All strings shoud be put in a one-per-line manner. save it as "structures.txt"
2. Prepare another text file that contains all the bioactivities in a one per line manner, to match up the first "bioactivity.txt" file

If you use Unix-like terminal, 
```
git clone https://github.com/quantaosun/QSAR-ML.git
```
then you can use Jupyter notebook to run the notebook in order.
# Drawbacks
There is no visulization, you may find hard to demonstrate your result to others, nevertheless, it is no less accurate to build QSAR compared to conventional field based 3D-QSAR.
