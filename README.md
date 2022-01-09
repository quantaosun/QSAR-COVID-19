# QSAR-ML
# If you don't have in-house compunds and bioactivity data, and want to obtain a QSAR from public data mining, please run part1.ipynb, if you have enough in-house data like more than 30 or more, you should start from 2end.ipynb
We will not discuss start from online as it is pretty straightforward, but foucus on the second senario

# Starting from you local structures and bioactivities
This repository is to build a QSAR model based on molecular descriptors and bioactivities, with the help of machine learning model random forest regression.

1. Prepare a text file that contains all the molecules' smiles string, you can obtain it from ChemDraw or any other means you prefer, note that there are various variants of smile, what I used here is the conventional one. All strings shoud be put in a one-per-line manner. save it as "smiles.text"
2. Prepare another text file that contains all the bioactivities in a one per line manner, to match up the first "smiles.text" file, i.e., the order and number should be the same.
3. Use the ipynb file I have provided here to start with these two files to start the journey of buiding this QSAR.

If you use Windows, just use mouse to download this github files as a ZIP file, then extract and enter the folder. It is assumed you got anaconda installed on your system, then
in conda prompt terminal, cd to this github folder, 

```
jupyter notebook QSAR-ML.ipynb
```
