# QSAR fro COVID-19
70% of the notebook coding are borrowed from https://github.com/dataprofessor as claimed inside some of the notebooks, with modification
30% of the notebook is written from scratch.
# Pre-conditions: Jupyter notebook
Windows, Mac or Linux erither is fine as long as you have a jupyter notebook installed.
# What is it does
As of January 9th 2022, the pandemic has been there for almost 2 years, with an unprecident nunber of infected people, there are also a great increse in relative research data like chemical compounds that could potentially inhibit the virous. To date when this is written, around 14,355 bioactivity toward small molecules, have benn recorded in the public chembl database. A fundamental question is then, can we build a QSAR model for all these data ? This is exactly what this project try to do. Not all bioactivities are comparable to each other, so this QSAR model will not be perfect but it will gives you some sense of the progress of small molecules based inhibitors against COVID-19.

This repository is to build a QSAR model based on molecular descriptors and bioactivities, with the help of machine learning model random forest regression, to build a QSAR model either based on public chembl bioactivity or your local bioactivity for SARS-COV-2, or if you could change the target, for any other target.

# 1. Starting from public data
This senario is not discussed for the moment, as it is easier to handle compared to the second.
# How to use it
run public.ipynb, 2,3,5 in sequence to build a QSAR, then run 3,5 of another repository https://github.com/quantaosun/QSAR-Chembl-Prediction to predict unknow molecules.

# 2. Starting from your local data
# How to use it
run local.ipynb, 2,3,5 in sequence to build a QSAR, then run 3,5 of another repository https://github.com/quantaosun/QSAR-Chembl-Prediction to predict unknow molecules.

Before you could run a local version, do the following before hand,

1. Prepare a text file that contains all the molecules' smiles string, you can obtain it from ChemDraw or any other means you prefer, note that there are various variants of smiles, what I used here is the conventional one. All strings shoud be put in a one-per-line manner. save it as "structures.txt", see the attatched example.
2. Prepare another text file that contains all the bioactivities in a one per line manner, to match up the first "bioactivity.txt" file, see the attached example.

If you use Unix-like terminal, 
```
git clone https://github.com/quantaosun/QSAR-ML.git
```
then you can use Jupyter notebook to run the notebook in order.
# Drawbacks
There is no visulization, you may find hard to demonstrate your result to others, nevertheless, it is no less accurate to build QSAR compared to conventional field based 3D-QSAR.
