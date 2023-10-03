---
layout: subpages1
title: BIG-MAP - WP5 - big data
description: Data structure and organization
---

Data organization is a fundamental task in general data analysis, regardless of the data type and size. It is essential for understanding the data and thus work efficiently. We propose following seven steps to effectively organize and handle the data.

## Here we describe seven steps to effectively organize and handle data.

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/8247947c-d9ca-4832-a160-2807076da3d5)

In the following we explain each of the steps:

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/bc92fa09-4897-46c2-a93f-5e9df63e1ae9){:height="50px"}

Consider using a hierarchical folder structure to categorize and store different types of data. The hierarchy will depend on the scientific goal.

{::options parse_block_html="true" /}
<details><summary markdown="span">Press for an example</summary>
  ```
ExperimentalData
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- ...
|   |   |   |-- SEM
|   |   |   |   |-- ...
|   |   |   |-- ...
|   |-- Sample_B
|   |   |-- ...
DataAnalysis
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- ...
|   |-- Sample_B
|   |   |-- ...
|-- Reports
|   |-- Sample_Type_Reports
|   |   |-- LNO_Gr
|   |   |   |-- ...
```
</details>
{::options parse_block_html="false" /}


![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/5bb703bb-c4d3-4608-8ce9-f60094525152){:height="50px"}

Consistent and descriptive names will make it easier to locate and understand the content of your data. For experimental data, it is good practice to name the folder with the acquisition date.

{::options parse_block_html="true" /}
<details><summary markdown="span">Press for an example</summary>
```
ExperimentalData
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- ExperimentalPreparation
|   |   |   |   |-- 02112023_run
|   |   |   |   |   | ...
|   |   |   |   |-- 30112023_run
|   |   |   |   |   | ...
|   |   |   |-- SEM
|   |   |   |   |-- ...
```
</details>
{::options parse_block_html="false" /}

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/a9f8b46a-19c3-4b69-aaf3-b1d3f705a34c){:height="70px"}

Separate raw, pre-processed, processed, and analyzed data: maintain separate folders or directories for each stage of data processing. This separation ensures that you can easily track the data's progression and avoid confusion (or worst, overwrite the raw data!).

{::options parse_block_html="true" /}
<details><summary markdown="span">Press for an example</summary>
```
ExperimentalData
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- ExperimentalPreparation
|   |   |   |   |-- 02112023_run
|   |   |   |   |   | -- rawdata
|   |   |   |   |   | -- preprocessed
|   |   |   |   |   | -- processed
|   |   |   |   |   | -- metadata
|   |   |   |   |-- ...
DataAnalysis
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- 02112023_run
|   |   |   |   |   | -- algorithms
|   |   |   |   |   | -- analyzed
|   |   |   |   |-- ...   
```
</details>
{::options parse_block_html="false" /}

![number4](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/068bbcae-68c6-44ca-a160-59bb02e26f5e){:height="50px"}

Keep a record of the steps and procedures you follow during data processing. Documenting your workflow will help you reproduce your results and troubleshoot any issues that may arise.
{::options parse_block_html="true" /}

<details><summary markdown="span">Press for an example</summary>
```
ExperimentalData
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- ExperimentalPreparation
|   |   |   |   |-- 02112023_run
|   |   |   |   |   | -- rawdata
|   |   |   |   |   | -- preprocessed
|   |   |   |   |   | -- processed
|   |   |   |   |   | -- metadata
|   |   |   |   |-- ...
DataAnalysis
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- 02112023_run
|   |   |   |   |   | -- algorithms
|   |   |   |   |   | -- analyzed
|   |   |   |   |   | -- documentation.txt
|   |   |   |   |-- ...   
|-- Reports
|   |-- Sample_Type_Reports
|   |   |-- Sample_A
|   |   |   |-- XRD_Report.pdf
|   |   |   |-- SEM_Report.pdf
|   |   |   |-- ...
```
</details>
<br/>

{::options parse_block_html="false" /}

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/fc18669b-27db-4fb3-8984-c8e487a03710){:height="50px"}

In the case your data undergoes iterative changes during analysis, using version control software (e.g. git) is a good practice to keep track of different versions and modifications. This can be particularly helpful when collaborating with other colleagues. There are many online free tutorials that can be followed to be able to use git.
(add tutorial?)

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/56865c6f-07e5-4139-b86f-8d6c1da9b120){:height="50px"}

Include metadata with your data to provide additional information about its characteristics, such as sample and any preprocessing steps applied. Well-documented metadata facilitates data discovery and understanding. A further step can be considered by ontologizing metadata following ontologies by WP7. This will be further developed by WP7.

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/2518deca-5e68-49ab-9b06-5babef35e4e6){:height="50px"}

Backup your data: regularly backup your data to prevent data loss using institutions’ servers, hard drives or cloud-based services. It may be helpful to set automatic synchronization routines, e.g. rsync, for specific directories.

  
## Example:
```
Experimental Data
|-- SampleType
|   |-- LNO_Gr
|   |   |-- CharacterizationTechniques
|   |   |   |-- XRD
|   |   |   |   |-- 20230115
|   |   |   |   |   |-- ExperimentalPreparation
|   |   |   |   |   |   |--…
|   |   |   |   |   |-- Data_Set_1
|   |   |   |   |   |   |-- rawdata
|   |   |   |   |   |   |-- processed
|   |   |   |   |   |   |-- metadatainformation.txt
|   |   |   |   |   |-- Data_Set_2
|   |   |   |   |       |-- rawdata
|   |   |   |   |       |-- processed
|   |   |   |   |-- SEM
|   |   |   |   |   |-- 20221210
|   |   |   |   |   |   |-- ...
|   |   |   |   |-- Transmission Electron Microscopy (TEM)
|   |   |   |       |-- 2022-03-20
|   |   |   |       |   |-- ...
|   |   |-- Si
|   |       |-- ...
|-- Metadata
|   |-- Sample_Type_Metadata.xlsx
|-- DataAnalysis
|   |-- SampleType
|   |   |-- LNO_Gr
|   |   |   |-- CharacterizationTechniques
|   |   |   |   |-- XRD_Analysis
|   |   |   |   |   |-- 20220115
|   |   |   |   |   |   |-- Analysis_Results
|   |   |   |   |   |-- SEM_Analysis
|   |   |   |   |   |   |-- ...
|   |   |   |   |-- TEM_Analysis
|   |   |   |       |-- 202203-0
|   |   |   |       |   |-- ...
|   |   |-- Sample_B
|   |       |-- ...
|-- Reports
|   |-- Sample_Type_Reports
|   |   |-- Sample_A
|   |   |   |-- XRD_Report.pdf
|   |   |   |-- SEM_Report.pdf
|   |   |   |-- TEM_Report.pdf
|   |   |-- Sample_B
|   |       |-- ...
|-- Raw Data (General)
|   |-- Sample_Type_Raw_Data
|   |   |-- Sample_A
|   |   |   |-- ...
|   |   |-- Sample_B
|   |       |-- ...
```


 

[back](BIGMAP-bigdata.md)
