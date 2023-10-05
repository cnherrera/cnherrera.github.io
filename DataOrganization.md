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
<details><summary markdown="span">**Press for an example of experimental report**</summary>

**Experimental report**

This is a basic example to document the experiment.

```
# X-ray Diffraction (XRD) Experiment Report

## Experiment Details
- Facility: ESRF
- Beamline Name/ID: [Beamline Name or ID]
- Experiment Date: [Date of the Experiment]
- Sample Description: [Description of the Sample]
- Incident X-ray Energy: [Energy in keV]

## Experimental Procedure
1. [Brief description of the experimental setup and sample preparation]
2. [Details of the XRD data collection procedure, including exposure times, angles, etc.]
3. [Any specific conditions or parameters used during the experiment]

## Data Collection
- Raw XRD Data Files: [List the file names or folder containing the raw data]
- Specifications: [Any specification on the rawdata needed for further processing]
- Scattering Angle Range: [Range in degrees]

## Conclusion
- [Summarize the main outcomes of the experiment]

```
</details>
{::options parse_block_html="false" /}


{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for an example of data analysis report**</summary>


**Data Analysis Report Template**

This a template with the basic structure to report data analysis. It has to be customized to fit the specific details and requirements of your technique and research objectives.

```
# XRD Data Analysis Report

## Analysis Details
- Experiment Date: [Date of the XRD Experiment]
- Data Source: [Specify the source of the XRD data, e.g., synchrotron ESRF]
- Data Calibration: [If applicable, mention any calibration steps]
- Data Analysis Software: []
- Data Processing: [Briefly mention any data processing step se.g., background subtraction, normalization] 
- Data Quality Control: [Describe checks for data quality and any outlier removal]


## Data Analysis
1. **Peak Identification**
   - [Identify and describe any observed peaks in the XRD pattern]
2. **Crystal Structure Determination**
   - [Discuss the crystal structure analysis results if applicable]
3. **Phase Analysis**
   - [Explain the phases present in the sample based on the XRD data]
4. **Texture Analysis**
   - [Discuss any texture information obtained from the XRD pattern]

## Results and Interpretation
- [Present the results of the data analysis, including identified phases, crystal structures, and any relevant findings]

## Discussion
- [Discuss the significance of the results and their implications for the research]

## Conclusion
- [Summarize the key findings and conclusions drawn from the XRD data analysis]

## References
- [Cite any references to relevant literature or software tools used in the analysis]

```


</details>
{::options parse_block_html="false" /}




![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/fc18669b-27db-4fb3-8984-c8e487a03710){:height="50px"}

In the case your data undergoes iterative changes during analysis, using version control software (e.g. git) is a good practice to keep track of different versions and modifications. This can be particularly helpful when collaborating with other colleagues. There are many online free tutorials that can be followed to be able to use git.

- Create github repository
- Code used for data handling and analysis will be maintained with version control.
- Observables can be shared with colleague.


{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for basic steps to use git**</summary>


## Git global setup
------------------
```
git config --global user.name "Your Name"
git config --global user.email "youremail@email.com"
```
  
## Use git locally in your machine.
```
1. In the directory  you want to create the repository, initialize new repository git
   git init
2. If you have already the files created, add them in the stagging phase
   git add .   # if you want to add specific files, change '.' by the name of the file
3. Commit the changes to your local repository
   git commit -m "updating files"
   Every time you modify your files, you have to "add" them to the stagging phase and then "commit"
4. Commit history can be displayed
   git log
```


## Push you local repertory to GitHub
```
git remore add origin <remote_repository_url>
# naming your branch "main"
git branch -M main 
and push to GitHub
git push -u origin main
```


## Using an existing repository on GitHub to modify files
```
git clone https://github.com/my/repository.git
cd repository
# modify any existing file, e.g. myscript.py
git status # check the current status
git add myscript.py # Add changes
git commit -m "updated script" # Commit changes (with a message)
git push origin branchname # Push changes on Github, branchname is typically main.
```

</details>
{::options parse_block_html="false" /}



![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/56865c6f-07e5-4139-b86f-8d6c1da9b120){:height="50px"}

Include metadata with your data to provide additional information about its characteristics, such as sample and any preprocessing steps applied. Well-documented metadata facilitates data discovery and understanding. A further step can be considered by ontologizing metadata following ontologies by WP7
(add example? how?)

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/2518deca-5e68-49ab-9b06-5babef35e4e6){:height="50px"}

Regularly backup your data to prevent data loss using institutions’ servers, hard drives or cloud-based services. It may be helpful to set automatic synchronization routines, e.g. rsync, for specific directories.


{::options parse_block_html="true" /}
<details><summary markdown="span">Press for an example</summary>
  
  For Unix-like system, it is helpful to create systematic synchronization of data. To do that, we need to create a cron job. We need to edit the cronjob as follows:
```
crontab -e
```
And it will be open to add a job. We want the synchronization to be done on Tuesdays and Fridays at noon:
```
0 12 * * 2,5 /path/to/rsync/myrsyncscript.sh
``` 
Create a myrsyncscript.sh that contains the syncrhonization command, and change the permission to be able to be executed for any user:
```
echo "rsync -avz /path/to/local/folder/ username@remote_server:/path/to/remote/folder/" > myrsyncscript.sh
chmod +x /myrsyncsync.sh
```
</details>
{::options parse_block_html="false" /}


* * * 


# Discussion

Add here any topic or question you would like to discuss.
Please modify the file: https://github.com/cnherrera/cnherrera.github.io/edit/master/DataOrganization.md


## Topic 1


## Topic 2



[back](BIGMAP-bigdata.md)
