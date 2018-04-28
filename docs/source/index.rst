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
=============================
|
2.1 Input 
----------
| A valid submitted gene expression file has the following format.  It is a TAB-delimited, plain text file with three columns (see the attached file for a full example).  The file contains an optional head line, followed by each gene's expression in a control sample (e.g., ControlSample) and in a treatment sample (e.g., KnockOutSample).
|
=============== =============== ===============
    gene_id      ControlSample   KnockOutSample
=============== =============== ===============
   AT1G01010	   1.198558083     2.036161827  
   AT1G01020   	13.75736234	     13.370796
   AT1G01030	   0.833779536	    0.203616183
   AT1G01040	   9.58846466	    7.126566394
   AT1G01046	        0	            0
   AT1G01050	   23.81482799	    21.10821094
   AT1G01060	   0.625334652	    1.221697096
   AT1G01070	   1.719670292	    0.950208853
   AT1G01080	   28.34850421	    25.24840665
   AT1G01090	   58.26034505	    42.96301455
   AT1G01100	   1066.508249	    1308.030358
   AT1G01110	   2.709783491	    1.425313279
=============== =============== ===============
|
2.2 Output
-----------------------
| The web application displays a table and a scatter plot given a gene expression file.
|
2.2.1 Table
>>>>>>>>>>>
| The table contains a list of differentially expressed genes with the following format:
=============== =============== =============== ===============
    gene_id      control_sample   treat_sample      log_2[FC]
=============== =============== =============== ===============
   AT1G01010      1.198558083      2.036161827        0.76
=============== =============== =============== ===============
|
2.2.2 Scatter plot
>>>>>>>>>>>>>>>>>>>>>
| The scatter plot displays differentially expressed genes.  The X-axis is Control, and Y-axis is Treatment.
 .. image:: /image/scatter_plot.png


3. Non-functional requirements
==============================
| A non-behavioral requirement describes a technical feature of a system, features typically pertaining to availability, security, performance, interoperability, dependability, and reliability. Non-behavioral requirements are often referred to as "non-functional" requirements due to a bad naming decision made by the IEEE (as far as I'm concerned non-functional implies that it doesn't work).
|

3.1 Response time 
------------------
| On the one hand, because the web application faces scientists all over the world, the number of users is more, and the requests for simultaneous processing are much more, so the response time must be reduced as much as possible. On the other hand, because a lot of data is huge, it needs to be analyzed for a long time, which will bring a poor user experience to the user, so our reaction time must be less than 5 seconds, which is an optimal reaction time.
| 
3.2 Aesthetic aspects
-------------------------
| Because this web application faces scientists all over the world, the interface must be internationalized, and it can support various languages such as English, Chinese, Korean and so on. Because this web application is the data analysis, so the interface as simple as possible, give scientists a rigorous style, so that the product is trustworthy. Since this web application is mainly fed by tables and scatter plots, the tables and scatter plots must be as clear as possible to make the data more explicit.
|
3.3 Confidentiality policy
------------------------------
| Ensuring the safety of the gene library is an integral part of our web application, and we must unconditionally guarantee the security of the user's data, as well as the results of each experiment. Most importantly, our web application serves scientists all over the world, so it requires more security and no data is leaked.
|
3.4 Availability
-----------------
| We must always consider the fault, consider how to expand, mitigate risk, monitor availability, Respond to usability problems in a predictive and determined way.
|
3.4.1 Always consider the fault
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
| The web application will always consider the response to the fault. For example, capturing the underlying exception, retrying logic, and circuit breakers, the circuit breaker mode is very useful in handling dependent failures, because they can reduce the impact of dependent failures on the system.
|
3.4.2 Always consider how to expand
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
| The web application will always consider how to expand. The system can now function properly, which does not mean that it will continue to operate properly tomorrow.The flow of most Web applications is increasing. A website that generates a certain amount of traffic today may produce much larger traffic than we think tomorrow.When we build the system, we will take into account future traffic. When most of the contents in the navigation bar are static content, we can dynamically add the change content to the page in the user's browser. By grouping these dynamic data and differentiating with static content, the performance of Web pages can be improved and the dynamic data amount needed to be processed by the application is reduced. This improves scalability and ultimately improves availability.
|
3.4.3 Mitigate risk
>>>>>>>>>>>>>>>>>>>
| The web application will always mitigate risk. When the system fails, we have identified the cause of the failure for risk before that. When the system becomes more and more complex, eliminating all risks is becoming more and more impossible. More of what we do is to manage the risks of the system, know what these risks are, which risks are acceptable, and what we can do to mitigate the risks.
|
3.4.4 Monitoring availability
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
| 1. Monitor the health of the server and ensure that they are always running effectively.
| 2. Monitor the configuration changes of the system to determine their impact on the application.
| 3. In depth understanding of applications and services to ensure that they are running as expected.
| 4. From the perspective of users, we can detect the running of applications in real time so as to find them before users really find problems.
|
3.4.5 Respond to usability problems in a predictive and determined way.
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
| When our web applications are faced with more and more users' needs and become more and more complex. Preparing for dealing with usability problems ahead of time is the best way to reduce the probability and severity of problems.
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
--------------
| When we design web applications, we have to consider web space. In a variety of factors, the web space of the software should not exceed the 1GB, not only convenient for the user to use this web application, but also to save a certain cost. On the other hand, it can provide more space for the users to analyze the data and identify the differential genes.
|
4.3 Budget
----------------
| Budget less than 10.000USD. Because financial resources, manpower and material resources are limited, if the budget exceeds the budget, then the project will be non-profitable, and there may still be in a loss.
|
4.4 System downtime
----------------------
| System downtime less than 30 minutes per year. Because too much system downtime will affect using, Greatly reducing the UE (user experience), thus reducing the rate of return.
|
5. Change cases
==================
| From speeding up recognition rate, Lifting accuracy, providing gene therapy plate, extending public gene bank, and providing private gene bank, we can improve the project.
5.1 Speed up recognition rate
-----------------------
| Identifying different genes reacts more quickly, saving scientists time, improving product efficiency and providing users with a better user experience.
|
5.2 Lifting accuracy
--------------------------
| The result is more precise and effective, reducing the number of repeated experiments, not only enhancing the reliability of products, but also enhancing the competitiveness of the industry.
|
5.3 Gene therapy plate
-------------------------
| In this web application, adding more plates to the genes, such as gene therapy, the identification of differential genes is used to search for a sequence of replacement genes that are more suitable for target cells, which makes it convenient for gene therapy, and our users can expand from scientists around the world to medical researchers, which can be said to be the gospel of human beings and a great leap in the field of gene therapy. This web application not only reduces the cost of gene therapy, but also improves the success rate of gene therapy.
|
5.4 Extended public gene bank
---------------------
| The identification of differential genes is used to search for a sequence of replacement genes that are more suitable for target cells, which makes it convenient for gene therapy, and our users can expand from scientists around the world to medical researchers, which can be said to be the gospel of human beings and a great leap in the field of gene therapy. This web application not only reduces the cost of gene therapy, but also improves the success rate of gene therapy.
|
5.5 Private gene bank
----------------------
| Users can add the different genes they have been looking for into their own private gene banks, and the private gene bank can list the generality and characteristics of the different genes that have been found, and more convenient for the user to study. Allowing users to register members not only enables users to get more storage space, but also has higher return on our projects.
|
6. Milestones
==================
| Submit SRS for review by May 1st.
| Get SRS approved by May 8th.
| Get design done by May 10th.
| Get coding done by May 24th.
| Acceptance tests by June 1st.
| Release by June 15th.
7. Appendices
==================
|
+------------+-----------------------------------------------------------------------------------------+
|Date        |   Change Log                                                                            |
+============+=========================================================================================+
|4.27        |   A brief introduction to the web application                                           |
+            +-----------------------------------------------------------------------------------------+
|            |   Analysis of the constraints faced by the project                                      |
+            +-----------------------------------------------------------------------------------------+ 
|            |   A milestone in the development of a project                                           |
+------------+-----------------------------------------------------------------------------------------+
|4.28        |  Analyze the functional requirements and non-functional requirements of the project     |
+            +-----------------------------------------------------------------------------------------+
|            |   image some improvements of the project                                                |
+------------+-----------------------------------------------------------------------------------------+
             
8. References
==================
| 1. ReStructuredText (RST) quick introduction grammar: 
     https://www.cnblogs.com/seayxu/p/5603876.html
|     



==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
