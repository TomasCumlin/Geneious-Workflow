# A Geneious Workflow for rapid detection of SARS-CoV-2

## 1 Introduction 

Clinical Microbiology at Uppsala University Hospital offers a workflow within the Geneious software that automates the final analysis steps in Nanopore sequencing of SARS-CoV-2. The idea is that the user only needs to import the fastq files into Geneious and have the workflow perform the rest of the analysis, without any manual work necessary from the user. The workflow also has the option to include pangolin and Nextclade lineage assignment as plugins in the workflow.

## 2 Files, Software & Set-up
Before you can import the workflow into Geneious, you need to ensure that you have all the files and software needed. If you plan to use the workflow that includes pangolin lineage assignment using the plugins pangolin and Nextclade, you will also need to do some manual modifications in some of the code (see 2.3).

### 2.1 Files required

This repository contains all files required to set-up the workflow in Geneious. Figure 1 illustrates what files are required depending on which workflow you plan to use and what operating system you have.



*Figure 1. What files you need to download depending on which workflow you will use and what operating system you have.* 

### 2.2 Software requirements

Before the workflow is set up, the user is expected to have the software presented in table 1 successfully installed.


*Table 1. A list of software required for a functioning workflow.*

Software
Version
Link
Required
Geneious Prime


geneious.com
✓
Python


python.org
✓
Java


java.com
✓
Docker Desktop




Required for the workflow with plug-ins
pangolin


cov-lineages
Required for the workflow with plug-ins
Nextclade CLI


Nextclade-cli
Required for the workflow with plug-ins



### 2.3 Manual modifications for the pangolin and Nextclade plugins
If you plan to use the workflow without the plugins, you can skip ahead to section X.X. 
If you plan to use the workflow **SARS-CoV-2 Sequence Assembly Midnight 5x Java Pangolin Nextclade.geneiousWorkflow**, manual modifications in some files are needed. Section 2.3.1 instructs how to modify the files for Windows. Section 2.3.2 instructs how to modify the files for Linux and Mac. 

#### 2.3.1 Set-up on Windows

To do the modifications, open the listed files in an editor of your choice. Thereafter, go to the specified lines within the code and modify according to the instructions.
##### pangolin

##### nextclade_windows_python.bat

**Line 6:*

```
<Path to Python installation location> <Path to location of the file *nextclade_windows.py* %1 %2
```

To see where Python is installed, open the terminal on your system and type:

```
where Python
```


#### nextclade_windows.py 

**Line 38:**

```
output_path=<path to where you want to save your files>
```
*Note that the variable **output_path** is a string, so the path must be in quotes.*
This is the directory to where the Nextclade output files will be stored.


**Line 56:**
```
nextclade_path=<path to where Nextclade is installed>
```
To see where Nextclade is installed, open the terminal on your system and type:
```
where Nextclade
```

Line 35 (optional):

```
path=""
```

If the file **nextclade.py** is only meant to be used as a plugin within Geneious, the variable **path** should be left as is, i.e. an empty string. Geneious will then run Nextclade in its own temporary folder during the analysis.
If **nextclade.py** is to be run outside of the workflow and outside of Geneious, **path** should have the directory of analysis assigned to it.





#### 2.3.2 Set-up on Linux or Mac

To do the modifications, open the listed files in an editor of your choice. Thereafter, go to the specified lines within the code and modify according to the instructions.

#### pangolin

#### nextclade.py

**Line 1:**
```
#! <path to Python installation directory>
```

Line 1 lets Geneious know that the file is to be interpreted as a Python file.
To obtain the Python directory on your system, open your terminal and type:

```
which python
```

Or if you have Python3 installed:

```
which python3
```

**Line 38:**

```
output_path=<path to where you want to save your files>
```
*Note that the variable **output_path** is a string, so the path must be in quotes.*
This is the directory to where the Nextclade output files will be stored.

**Line 56:**

```
nextclade_path=<path to where Nextclade is installed>
```

To obtain the Nextclade directory on your system, open your terminal and type:

```
which Nextclade
```

Line 35 (optional):
```
path=""
```
If the **nextclade.py** is only meant to be used as a plugin within Geneious, the variable **path** should be left as is, i.e. an empty string. Geneious will then run Nextclade in its own temporary folder during the analysis.
If **nextclade.py** is to be run outside of the workflow and outside of Geneious, **path** should have the directory of analysis assigned to it.


## Import the workflow to Geneious


## Manual settings in Geneious

## Running the workflow in Geneious

### Input data

### Output data

## References 

 
