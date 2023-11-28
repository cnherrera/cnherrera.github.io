---
layout: subpages1
title: Characterization techniques - big data
description: Data structure and organization
---

Data organization is a fundamental task in general data analysis, regardless of the data type and size. It is essential for understanding the data and thus work efficiently. We propose following seven steps to effectively organize and handle the data.

## Here we describe seven steps to effectively organize and handle data.

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/8247947c-d9ca-4832-a160-2807076da3d5)

In the following we explain each of the steps:

![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/bc92fa09-4897-46c2-a93f-5e9df63e1ae9){:height="50px"}

Consider implementing a hierarchical folder structure to systematically categorize and store different types of data. The hierarchy will depend on the scientific goal.

{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for an example on data structure**</summary>
```shell
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
<details><summary markdown="span">**Press for an example for naming convention**</summary>
```shell
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
<details><summary markdown="span">**Press for an example**</summary>
```shell
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

This is a basic example to document the experiment.

```yml
# X-ray Diffraction (XRD) Experiment Report

## Experiment Details
- Facility: [e.g. ESRF]
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

This a template with the basic structure to report data analysis. It has to be customized to fit the specific details and requirements of your technique and research objectives.

```yml
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

{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for basic steps to use git**</summary>

**Git** is a distributed version control system. It works locally on your machine, allowing you to track changes, create branches, and merge code changes.

**GitHub** is a web-based platform and hosting service for `git` repositories.

## Git global setup

It is good practice to configurate your 'git' environment.  Your name and email will be used to identify you every time you commit (authorship for changes). 
```shell
git config --global user.name "Your Name"
git config --global user.email "youremail@email.com"
```
  
## Use git locally in your machine.

1. In the directory you want to create the repository, initialize new git repository. This will create an empty hidden .git folder 
```shell
git init   # initializing empty git repositorty
git status  # to check the status of the repository: On branch master, No commits yet, nothing to commit 
```  
2. If you have already the files created, add them to the virtual repository
```shell
git add .   # add all files in the current directory to the virtual repository
git add myfile.txt  # add a specific file
git status  # check status: On branch master, No commits yet, Changes to be committed-> new file:   myfile.txt

```
3. Commit the changes to your local repository
```shell
git commit -m "My comment: adding a new file"   # Commit the changes with a descriptive message, files are added to your repository.
```
   Every time you modify your files, you have to "add" them to the virtual repertory and then "commit"
4. Commit history can be displayed
```shell
git log   # commit history with reference
```
This is what is displayed. 'HEAD' means that this is the, and `master` means that we are looking at the commit history for the "master" branch.
```shell
commit f9c00170d3c09a6731b315b91b7863da91eec9d6 (HEAD -> master)
Author: Cinthya Herrera <herrerac@ill.fr>
...
```


## Push you local repository to GitHub
You can push your local repository to GitHub as follows:

```shell
git remote add origin <remote_repository_url>
git branch -M main  # naming your branch "main"
git push -u origin main # and push to GitHub
```


## Using an existing repository on GitHub to modify files
```shell
git clone https://github.com/my/repository.git  # clone existing repository
cd repository  # enter to the repository  directory
# modify any existing file, e.g. myscript.py
git status # check the current status
git add myscript.py # Add changes
git commit -m "updated script" # Commit changes (with a message)
git push origin branchname # Push changes on Github, branchname is typically main.
```

add branching, etc


There are many tutorials one can follow to learn git. Some of them:

<a href="https://githowto.com/">General git tutorial 1</a>

<a href="https://gitimmersion.com/">General git tutorial 2</a>

<a href="https://learngitbranching.js.org/">Learn git branching interactively</a>

    

</details>
{::options parse_block_html="false" /}


![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/56865c6f-07e5-4139-b86f-8d6c1da9b120){:height="50px"}

Include metadata alonside your data to provide supplementary information crucial forunderstandind the dataset. This information can include specifics regarding the sample and experiment, as well as any preprocessing procedures applied. Well-documented metadata facilitates data discovery and understanding.


{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for a discussion on ontologizing metadata**</summary>

A further step can be considered by ontologizing metadata following ontologies.
- why it is important?
- Give an example
- Needs for more development on the behind the scenes (RDP)
- add links on things that are currently working.


</details>
{::options parse_block_html="false" /}



![image](https://github.com/cnherrera/cnherrera.github.io/assets/25098422/2518deca-5e68-49ab-9b06-5babef35e4e6){:height="50px"}

You should regularly backup your data to prevent data loss using institutions’ servers, hard drives or cloud-based services. It may be helpful to set automatic synchronization routines for specific files or directories.


{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for an example to automate synchronization**</summary>
  
  For Unix-like system, it is helpful to create systematic synchronization of data. To do that, we need to create a cron job. We need to edit the crontab as follows:
```shell
crontab -e
```
this will open an editor in which you should specify the frequency of the synchronization, here we set it to every Tuesday and Friday at noon:
```shell
0 12 * * 2,5 /path/to/rsync/myrsyncscript.sh
``` 
You need to create the script myrsyncscript.sh containing the syncrhonization command, and change the permission to be able to be executed for any user:
```shell
echo "rsync -avz /path/to/local/folder/ username@remote_server:/path/to/remote/folder/" > myrsyncscript.sh
chmod +x /myrsyncsync.sh
```
</details>
{::options parse_block_html="false" /}


* * * 


# Discussion

Add here any topic or question you would like to discuss.
Please modify the file: 
          <a href="https://github.com/cnherrera/cnherrera.github.io/blob/master/DataOrganization.md">Edit Data Organization</a>
    

## Topic 1
[Add topic here]


## Topic 2
[Add topic here]


[back](bigdata.md)
