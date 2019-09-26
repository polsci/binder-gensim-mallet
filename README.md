# Binder + Gensim + Mallet

September 26, 2019  
Geoff Ford  
https://geoffford.nz  
https://github.com/polsci/  

## Introduction

This repository is designed for students in DIGI405 at the University of Canterbury to do topic modeling through their browser using Binder. It is relevant for others who want to do topic modeling through a browser with their own corpus.

## A note to DIGI405 students

Make sure you are downloading your notebook regularly as Binder times out. Read the [Binder FAQ](https://mybinder.readthedocs.io/en/latest/faq.html).

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
