# QSAR fro COVID-19
Around 60% of the notebook coding, especially the key method of calculating molecular descriptors are borrowed from https://github.com/dataprofessor as claimed inside some of the notebooks.

Around 40% of the notebook is written from scratch, especially the local version.

![image](https://user-images.githubusercontent.com/75652473/148683133-8342aa53-e92b-4fc2-bb56-8d1a5ef02eac.png)
![image](https://user-images.githubusercontent.com/75652473/148683515-e270c7b4-61b7-48f7-88fa-2d2080edb611.png)


--------------100% as training set---------------------- 80% as training set

![image](https://user-images.githubusercontent.com/75652473/148683138-cafaf08c-de90-4930-9d64-45b329345e52.png)

----------20% tested


# Pre-conditions: Jupyter notebook
Windows, Mac or Linux either is fine as long as you have a Jupyter notebook installed.
# What is it does
As of January 9th 2022, the pandemic has been there for almost 2 years, with an unprecedented number of infected people, there is also a great increase in relative research data like chemical compounds that could potentially inhibit the virus. To date when this is written, around 14,355 bioactivities toward small molecules, have been recorded in the public Chembl database.

A fundamental question is then, can we build a QSAR model for all these data? This is exactly what this project tries to do. Not all bioactivities are comparable to each other, so this QSAR model will not be perfect but it will give you a sense of the progress of small-molecules based inhibitors development against COVID-19.

The QSAR model is to take molecular descriptors as independent variables,  and bioactivities as dependent variables, with the help of machine learning model random forest regression, to build a QSAR model either based on public Chembl bioactivity or your local bioactivity for SARS-COV-2 or if you could change the target, for any other target.

# 1. Starting from public data

# How to use it
run 1_public.ipynb, 2_build_public,3_build_public,5_build_all in sequence to build a QSAR, then run 3_external_prediction,5_external_prediction to predict unknown molecules.

Before you could do the external prediction, you should create a file called "unknow.txt" containing all the smiles you want to predict or validate.

# 2. Starting from your local data
# How to use it
run 1_local.ipynb, 3_build_local,5_build_all in sequence to build a QSAR, then run 3_external_prediction,5_external_prediction to predict unknown molecules.

Before you could run a local version, do the following beforehand,

1. Prepare a text file that contains all the molecules' smiles string, you can obtain it from ChemDraw or any other means you prefer, note that there are various variants of smiles, what I used here is the conventional one. All strings should be put in a one-per-line manner. save it as "structures.txt", see the attached example.
2. Prepare another text file that contains all the bioactivities in a one per line manner, to match up the first "bioactivity.txt" file, see the attached example.

Before you could do the external prediction, you should create a file called "unknow.txt" containing all the smiles you want to predict or validate.

Windows: Directly download the ZIP file and extract it to use.

Unix-like terminal and Mac
```
git clone https://github.com/quantaosun/QSAR-ML.git
```
then you can use Jupyter notebook to run the notebook in order.
# Note
For the sake of this example, I only used 139 molecules with IC50, but there are actually thousands of other bioactivities available out there, so check it out yourself and see if you could improve the model performance.

在全球新冠病毒感染人数激增的同时，针对该病毒的小分子化合物活性数据也在快速增长，如何分析理解这些数据对于最终研制小分子化学特效药至关重要。这个项目展示了如何使用基于机器学习的定量构效关系，以化学分子的分子描述符为自变量，对病毒的半抑制浓度为因变量，进行了定量分析，构建了数学模型，可以帮助人们理解已知化合物的表现，以及预测未知化合物的表现。本项目提供了两个途径来构建模型，第一种为基于公开数据库的方式，第二为基于本地未公开数据的方式。

本项目遵循训练，测试，和外部（预测）验证，三个步骤，经过一个简单的基于IC50 的新冠病毒的139个化合物的学习，测试，发现此种情况下的模型完全无法正确预测内部测试集合，因此没有必要继续外部（预测）验证，但这并不代表模型的构建方法有问题，而可能是数据集本身的体量太小。因时间原因我本次计算只使用了含有IC50 记录的139个小分子，理论上如果更换为其他数量更多的生物活性指标，模型的表现有望提高。

经过简单的修改，该方法可拓展到任何其他药物靶点，默认采用的分子描述符为pubchem分子描述符，经过修改也可采用诸如RDKT 分子描述符等，而数学建模也采用了机器学习中常见的随机森林回归模型，自变量的维度达到了几百个，相对于传统的几个几十个的分子描述符更容易捕捉到决定分子活性的背后因素。

当使用80%作为训练集，来预测20%时，第三张图表现很差，预测与实际有较大偏差，随着化合物数量的的进一步增长，未来该方法的表现可能会有所提高。本项目并不能提供一个完美的预测新冠病毒的模型，全世界的科学家到今天也很难有人做到这一点，这个方法主要是提供思路和提供讨论的空间。或者，对于其他的非新冠病毒靶点，如果你有大量的本地数据，靶点也更为成熟，那么该模型的表现或许会有明显的提升，该方法很可能会优于传统的3D-QSAR，特别是当你有海量数据需要总结处理的时候。
