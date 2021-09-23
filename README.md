# Binder + Gensim + Mallet

September 23, 2021  
Geoff Ford  
https://polsci.github.io/  
https://github.com/polsci/  

See also: [Colab + Gensim + Mallet](https://github.com/polsci/colab-gensim-mallet)

## Introduction

This repository is designed for students in DIGI405 at the University of Canterbury to do topic modeling through their browser using Binder. It is relevant for others who want to do topic modeling through a browser with their own corpus.

Note: The notebook has been updated to enforce Gensim v3.8 (the last version to support running topic models via Mallet) and to specify requirements using an apt.txt file and requirements.txt file over the former Dockerfile.

## A note to DIGI405 students

Make sure you are downloading your notebook regularly as Binder times out after 10 minutes! Read the [Binder FAQ](https://mybinder.readthedocs.io/en/latest/faq.html).

### Steps for DIGI405:

1. Launch Binder (see link below).  
2. Using the file browser upload your corpus zip file (from the Datasets page on Learn).   
3. Run the `topic-modeling-with-gensim-mallet.ipynb` notebook.
4. Run the first code cell in the notebook to unzip the corpus.  
5. Use the notebook to create your topic model.  

## A note to everyone

Before running the Binder, please read the [Binder FAQ](https://mybinder.readthedocs.io/en/latest/faq.html) as it contains information on Binder, resource limits, and especially **how long your session will last**!

## Launch Binder

Click here to run the Binder:  
[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/polsci/binder-gensim-mallet/master)

## Not in DIGI405?

If you are not from this course, you can of course upload your own corpus as a zip. Your corpus should consist of a single directory of txt files (one document per txt file). Be aware though that [resources are limited](https://mybinder.readthedocs.io/en/latest/faq.html) (e.g. max RAM limits). It has been tested with a corpus of < 40mb across 3600+ txt files. It is unlikely to work with very large corpora due to the memory requirements. This isn't the fastest way to run topic models, but allows you to create a topic model through your browser without installing any software.

## A note about pyLDAvis

The environment should support [pyLDAvis](https://github.com/bmabey/pyLDAvis), however this is not implemented in the sample notebook. Add a cell like this to run it (note: this is sloooowwww and not recommended!):

```
import pyLDAvis.gensim as gensimvis
import pyLDAvis
vis_data30 = gensimvis.prepare(gensimmodel30, doc_term_matrix, dictionary)
pyLDAvis.display(vis_data30)
```
