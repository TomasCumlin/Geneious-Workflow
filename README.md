# A Geneious Workflow for rapid detection of SARS-CoV-2

## Set-up in Linux

### nextclade.py

Open the file **nextclade.py** with the editor of your choice. There are 3 lines which must be modified by the user and 1 line that is optional.

**Line 1:**
```
#! <path to Python installation directory>
```
Line 1 lets Geneious know that the file is to be interpreted as a Python file.
To obtain the Python directory on your system, open your terminal and type:
which python
Or if you have Python3 installed:
which python3

**Line 38:**
```
output_path=<path to where you want to save your files>
```
Note that the variable **output_path** is a string, so the path must be in quotes.
This is the directory to where the Nextclade output files will be stored.

**Line 56:**
```
nextclade_path=<path to where Nextclade is installed>
```

To obtain the Nextclade directory on your system, open your terminal and type:
which Nextclade

Line 35 (optional):
