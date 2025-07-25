# CountingGenesWithBash

## Computational Practice: How many genes are in human, yeast, and rice genomes?	

## Lab Overview
Each individual from a population is unique because of genetic and environmental variation of gene expression.  Over the years, bioinformaticist and other scientists have discovered reference gene sets for many organisms.  All reference gene sets will never be perfect, but they provide an excellent baseline to discover the meaning of gene expression.  In this lab, you will download the reference gene sets for 3 organisms and learn how to look at these FASTA formatted files using the Linux command line.

## Lab Objectives:
•	Access the Palmetto2 cluster
•	Find gene sequence files at Ensembl
•	Download, move, and uncompress files on a Linux system.
•	Use the properties of a FASTA formatted file to count sequence records
Follow these lab instructions:

## Task A: Start a Jupyter Notebook interactive node on Palmetto2 
* You have been granted a full feature educational account on the Palmetto2 cluster.
* To access the remote computer, open a web browser (Chrome, Safari, Edge, etc.) and go the the Clemson Ondemand site:  [Palmetto2](https://ondemand.rcd.clemson.edu)
* Start an interactive apps>>Jupyter Notebook session.  Change these resource allocations: CPU=4, memory=64GB, Number of Hours=12. This will create a 12 hour interactive session and allow you to interface with the cluster. When you launch new sessions, you can change the resource allocation if necessary.
* Once launched, open a terminal to interact with the cluster in the bash environment using a CLI.
* Create a working directory in /scratch/$USERNAME ($USERNAME=Your Clemson Useer ID)

## Task B: Download the human gene set.
NOTE: Anything with single quotes is to show it is a string.  Don’t paste the quotes on the command line.  Don’t be afraid to explore!

1. Using the Chrome browser on your local computer, go to the Ensembl website at [https://uswest.ensembl.org].  Explore the website.
2. Select the Homo sapiens species.  Check out the “More information and statistics” for statistics on the human reference genome assembly.
3. Go to the ‘Download FASTA files for genes, cDNAs, ncRNA, proteins’ link.   Go to the cDNA folder. Read the README file to find the gene set.
4. Right click on the correct cDNA file and copy the link address (URL) to the file.
5. Download the human cDNA file using 'wget' command and the file URL in the working directory.
6. Uncompress the gz file (‘gunzip’).

## Task C: Download the yeast gene set.
1. Using the Chrome browser on your local computer, go to the Ensembl website at [https://uswest.ensembl.org].  Explore the website.
2. Select the Saccharomyces cerevisiae species.  Check out the “More information and statistics” for statistics on the yeast reference genome assembly.
3. Right click on the correct cDNA file and copy the link address (URL) to the file.
4. Download the yeast cDNA file using 'wget' command and the file URL in the working directory.
5. Uncompress the gz file (‘gunzip’) .

## Task D: Download the rice gene set.
1. Using the Chrome browser on your local computer, go to the Ensembl Plants website at [https://plants.ensembl.org/index.html].  Explore the website.
2. Select the Saccharomyces cerevisiae species.  Check out the “More information and statistics” for statistics on the yeast reference genome assembly.
3. Right click on the correct cDNA file and copy the link address (URL) to the file.
4. Download the rice  cDNA file using 'wget' command and the file URL in the working directory.
5. Uncompress the gz file (‘gunzip’) .
   
## Task E: Count the number of sequences in the cDNA files.
These sequences are in FASTA format which means each sequence record starts with a ‘>’.  Thus if you know how to count the number of lines in a file that starts with  ‘>’, you will know how many sequences are in the files.  Your task is to count the number of sequences in each of the three files you downloaded.  Copy and paste the command lines you used along with the sequence counts in a text file. Place this text file in the Homework folder on the Desktop.

CLUE A: To look at the top and bottom 10 lines of each file, use the ‘head’ and ‘tail’ command, respectively.  To see all lines in a file, use the ‘cat’ command.  These are big files so it will take a while to send all the data to the screen.  NOTE: You can stop a command by pressing CTRL-C on your keyboard.

CLUE B: To find a text pattern (e.g. ‘>’) in a file, use the ‘grep’ command.  

CLUE C: To count the number of lines in a file, use the ‘wc -l’ command.

CLUE D: To string multiple commands together, use the pipe command ‘|’. 

For example, this command line will open a file and count the number of lines in the file:

```
cat Homo_sapiens.GRCh38.cdna.all.fa | wc -l
```

For example, this command line will open a file and count the number of lines that have the pattern ‘AAATTTGGG’:
```
cat Homo_sapiens.GRCh38.cdna.all.fa | grep ‘AAATTTGGG’
```
