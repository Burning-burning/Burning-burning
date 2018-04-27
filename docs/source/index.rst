.. hello documentation master file, created by
   sphinx-quickstart on Thu Apr 26 22:46:35 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Software Requirements Specification for OMG Version 0.1
===============================

.. toctree::
   :maxdepth: 2
   :caption: Contents:
   
Group information
=================
Group name
-----------------
| Burning-burning
|
Group members:
-----------------
| 1. 石洪霞(Sherry 201632120113): 1054689185@qq.com
| 2. 刘会翠(Sally 201632120111): 572931147@qq.com
|
1. Interoduction
=================
| The purpose of this document is to identify differentially expressed genes by comparing different expressions of samples and processed samples, that is, "Oh My Genes".
|
1.1 Purpose
-----------------
| Through our scientists uploading the gene expression file, identifying differentially expressed genes given a gene expression file containing two cell samples, quickly obtaining the differentially expressed genes and feedback the results to the scientists, so that scientists can better understand the mystery of gene expression.
|
1.2 Overview
-----------------
| The web application has a simple interface with a single button [Upload and GO].  Our scientists upload a plain text file containing gene expression levels from two samples, representing two experimental conditions.  Accepting the file, the software will return a table of differentially expressed genes and a scatter plot of these genes whose X-axis is control and Y-axis is treatment.  If an invalid gene expression is given, the web application returns a page informing the user to provide the correct format.
|
1.3 User characteristics
-----------------
| end-users: Scientist who studies gene expression.
| web site maintainers: Programer
|
1.4 Conventions, acronyms, abbreviations, terminology, glossary
-----------------
|
1.4.1 Conventions
>>>>>>>>>>>>>>>>>
| Scientists must abide by the confidentiality agreement, not to be allowed to publicize the differential genes without permission, not to sell the research results illegally, and not to use the results of the research for illegal use, that is, to destroy human harmony and destroy social stability.
|
1.4.2 Acronyms
>>>>>>>>>>>>>>>>>
| OMG - Oh My Genes, that is, the peroject name.
| logFC - log fold change of gene expression.  log_2 [T/C], where T is the gene expression level from a treatment sample, while C is the gene expression level from a control sample.


==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
