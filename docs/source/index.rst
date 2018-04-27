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
| The purpose of this section is to introduce conventions, acronyms, abbreviations, terminology, glossary, it can help you get a better understanding of the project.
|
1.4.1 Conventions
>>>>>>>>>>>>>>>>>
| Scientists must abide by the confidentiality agreement, not to be allowed to publicize the differential genes without permission, not to sell the research results illegally, and not to use the results of the research for illegal use, that is, to destroy human harmony and destroy social stability.
|
1.4.2 Acronyms & Abbreviations
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
| OMG - Oh My Genes, that is, the peroject name.
| logFC - log fold change of gene expression.  log_2 [T/C], where T is the gene expression level from a treatment sample, while C is the gene expression level from a control sample.
|
1.4.3 Terminology & Glossary
>>>>>>>>>>>>>>>>>>>>>>>>>>>>
| Control sample - a cell sample prepared in its normal condition.
| Treatment sample - a cell sample treated by special chemicals, or in which some genes are altered.
| Differentially expressed genes - the genes which have significantly different expression levels between two samples.
| Up-regulation - a gene is said to be up-regulated if it has higher expression in treatment than in control.
|
2. Functional requirements
===========================
|
2.1 
-----------------------
|
3. Non-functional requirements
==============================
|
4. Constraints
=============================
| The software is based on gene research, at the same time, some constraints must be considered in order to make the software more reasonable and reduce the cost.
|
4.1 Browser compatibility
---------------------------
| In order to make the software adapt to different users around the world, and to facilitate users to use their familiar browsers, the software must be compatible with the various browsers, that is, Firefox, Chrome, Safari, IE and so on.
|
4.2 Web Space
===================
| When we design web applications, we have to consider web space. In a variety of factors, the web space of the software should not exceed the 1GB, not only convenient for the user to use this web application, but also to save a certain cost. On the other hand, it can provide more space for the users to analyze the data and identify the differential genes.
|
4.3 Budget
===================
| Budget less than 10.000USD. Because financial resources, manpower and material resources are limited, if the budget exceeds the budget, then the project will be non-profitable, and there may still be in a loss.
|
4.4 System downtime
====================
| System downtime less than 30 minutes per year. Because too much system downtime will affect using, Greatly reducing the UE (user experience), thus reducing the rate of return.
|



==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
