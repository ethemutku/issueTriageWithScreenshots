# Improving Issue Triage with Attached Screenshots

This project improves **IssueTAG [1]** with the use of screenshots attached to issue reports in our industrial case ([Softtech Inc.](https://softtech.com.tr/)). It includes code on how we include textual and visual features extracted from the subject, description and screenshot attachments in our classification pipeline. 

Due to security and privacy reasons, we are able to publish (in full, or in partial) neither the issue reports used in these studies nor the scripts regarding the **SVM_TA_2** model described in our paper. However, other scripts, which are similar to the ones we used in order to carry out the experiments for the issue assignment approach to include screenshot attachments, can be found in this repository. 

## IssueTAG

**IssueTAG** is a software issue report assignment tool, which has been fully operational in an industrial setting since Jan 12, 2018, making automated assignments for all the issue reports submitted in the industrial setting [IssueTAG](https://github.com/ethemutku/IssueTAG) [1]. In this work, we show that we can improve its performance by using the screenshots attached to the issue reports. This repository includes the scripts which are similar to the ones we used in order to carry out the experiments.

## Getting Started

The repository includes the following **Jupyter Notebook** scripts coded with **Python 3.9**: 

* multi_source.ipynb
* single_source_image.ipynb
* single_source_text.ipynb

We recommend you to download [Anaconda](https://www.anaconda.com/products/distribution) which also installs **Jupyter Notebook** on your computer with most of the packages needed. The following packages are needed to run the scripts, which can be easily installed with the **pip install ...** command in **Anaconda Prompt**. 

* re
* pandas
* numpy
* matplotlib 
* stop_words
* sklearn
* keras
* tensorflow

Before running any script, the issue reports should have been downloaded and saved as a csv file. If you have a stop-word list, assign the list to the variable "stop_word_list". 

Some of the issue reports in the csv file will be used as training data and some of them as test data. So, decide on the issue reports to be used as training data, and the issue reports to be used as test data (i.e. the year and month/s they are created) before running the scripts. Logically, the creation date of issue reports to be used as test data should be after the creation dates of issue reports to be used as training data. 

All of the three scripts will ask you the name of the issue report file, and then, the creation year and months of training and test issue reports for filtering. They will automatically compose the training and testing data, and pre-process the textual data to obtain the related tf-idf representations. 

The single-source approaches that use textual information only (i.e. single_source_text.ipynb), use the **subject** and **description** attributes of an issue report, which should be provided in the input csv file. 

The single-source approaches that use visual information only (i.e. single_source_image.ipynb), use the attached screenshots as input. 

The single-source approaches that use visual information only (i.e. single_source_image.ipynb), use both. 

## References

[[1] Aktas, E.U. & Yilmaz, C. (2020). Automated Issue Assignment: Results and Insights from an Industrial Case. Empirical Software Engineering Journal, 25, 3544-3589.](https://link.springer.com/article/10.1007/s10664-020-09846-3)
