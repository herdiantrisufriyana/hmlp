# Human and machine learning pipelines for responsible clinical prediction using high-dimensional data

Herdiantri Sufriyana, MD, MSc; a, b Yu-Wei Wu, PhD; a, c Emily Chia-Yu Su, PhD 
a, c, d, *

a Graduate Institute of Biomedical Informatics, College of Medical Science and Technology, Taipei Medical University, 250 Wu-Xing Street, Taipei 11031, Taiwan.
b Department of Medical Physiology, Faculty of Medicine, Universitas Nahdlatul 
Ulama Surabaya, 57 Raya Jemursari Street, Surabaya 60237, Indonesia.
c Clinical Big Data Research Center, Taipei Medical University Hospital, 250 
Wu-Xing Street, Taipei 11031, Taiwan.
d Research Center for Artificial Intelligence in Medicine, Taipei Medical 
University, 250 Wu-Xing Street, Taipei 11031, Taiwan.
\* Corresponding author at: Clinical Big Data Research Centre, Taipei Medical 
University Hospital, 250 Wu-Xing Street, Taipei 11031, Taiwan. Phone: 
+886-2-66382736 ext. 1515.

The preprint can be found here: (soon)

The journal article will be published soon.

Supplementary Information and other files can be found in any of above 
publications.


## System requirements

We used R 4.0.2 programming language (R Foundation, Vienna, Austria) to conduct 
most steps of the data analysis. For steps related to the deep-insight visible 
neural network (DI-VNN), we also used Python 3.6.3 programming language 
(Anaconda Inc., Austin, TX, USA). The integrated development environment 
software was RStudio 1.3.959 (RStudio PBC, Boston, MA, USA). To ensure 
reproducibility, we used Bioconductor 3.11;61 thus, versions of the included R 
packages were all in sync according to versions in this Bioconductor version. 
For all models except the DI-VNN, we used an R package of caret 6.0.86 that 
wraps R packages for the modeling algorithms, which were glmnet 4.1, Rborist 
0.2.3, and gbm 2.1.8. For the DI-VNN, we used keras 2.3.0 and tensorflow 2.0.0 
Python libraries via R packages of reticulate 1.16, keras 2.3.0.0, and 
tensorflow 2.0.0. We also created R packages and a Python library for many 
steps in the data analysis, including the DI-VNN, which are: 
[medhist 0.1.0](https://github.com/herdiantrisufriyana/medhist), 
[gmethods 0.1.0](https://github.com/herdiantrisufriyana/gmethods), 
[rsdr 0.1.0](https://github.com/herdiantrisufriyana/rsdr), 
[clixo 0.1.1](https://github.com/herdiantrisufriyana/clixo), and 
[divnn 0.1.3](https://github.com/herdiantrisufriyana/divnn) (both an R package 
and Python library)
For model deployment, we used Shiny Server 1.4.16.958 and Node.js 12.20.0. 
Details on other R package versions and all of the source codes (vignette) for 
the data analysis are available in hmlp.Rmd.

To reproduce our work, a set of hardware requirements may be needed. We used a 
single machine for all models, except the DI-VNN, with 16 logical processors 
for the 2.10 GHz central processing unit (CPU) (Xeon?? E5-2620 v4, Intel??, Santa 
Clara, CA, USA), 128 GB RAM, and 11 GB graphics processing unit (GPU) memory 
(GeForce GTX 1080 Ti, NVIDIA, Santa Clara, CA, USA). Parallelism was applied 
for CPU computing. Meanwhile, the DI-VNN required a higher GPU capability than 
that provided by the previous specification. For hyperparameter tuning and 
training, we used multiple machines in a cloud with 90 GB RAM and 32 GB GPU 
memory (Tesla V100-SXM2, NVIDIA, Santa Clara, CA, USA). For predictions, the 
DI-VNN only needed a CPU in a local machine, or that in a cloud machine for the 
web application.


## Installation guide

Please follow through the R Markdown (hmlp.Rmd). Installation approximately 
requires ~15 minutes.


## Demo

All codes require ~30 minutes to complete for non-expensive computation. We 
provided pre-existing files to substitute the expensive computation. One can 
set a variable that defines whether the expensive parts will be conducted. This 
may take 1 hour to 8 days to complete, but not including processes for finding 
causal factors.

We also provide small datasets to demo the 5 packages we made for this study. 
Please follow through the vignettes. These show simple examples to demo the 
packages.


## Instructions for use

Briefly, all system requirements, installation guide, demo, and instructions 
for use are available in R Markdown (hmlp.Rmd) and other files in this 
repository.

The R Markdown (.Rmd) contains the same texts with this document but including 
the programming codes for the data analysis in-between as shown in 
Supplementary Information.

Nevertheless, one cannot run the markdown or script unless having the raw 
dataset. To get raw data, one need to request an access from the BPJS Kesehatan 
for their sample dataset published in August 2019. Up to this date, there are 
three sample datasets they published in February 2019, August 2019, and 
December 2020. For the first and second versions, a request is applied via 
https://e-ppid.bpjs-kesehatan.go.id/, while the third is applied via 
https://data.bpjs-kesehatan.go.id.

To preprocess the raw data into the input dataset of this study, follow the 
codes of the R Markdown in data.Rmd: 
https://github.com/herdiantrisufriyana/medhist/tree/main/preprocessing.
