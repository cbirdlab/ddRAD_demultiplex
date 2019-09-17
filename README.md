# *RAD_demultiplex

Scripts to demultiplex internally barcoded fastq files on a SLURM scheduled HPC cluster in parallel.  With some mild hacking, this will run on a workstation in bash.  Demultiplexed fastq files are saved to directories in the `pwd`.

ddRAD_demultiplex.sbatch is for double-digest RAD data

newRAD_demultiplex.sbatch is for single-digest RAD data that has 1 ligated barcode followed by ezRAD sequencing (aka newRAD or bestRAD)
* Note that `process_radtags` which is harnessed by this script cannot handle
  * The remaining restriction site before the barcode, for SbfI, it's `GG`, so it should be added to the barcode in the demultiplex decode files
  * Indels at the beginning of the sequence, which are quite common - I have to code a solution to this using `agrep `

## To Run

Clone this repo to your computer
```
git clone 

No commandline arguments are accepted.  To specify where your data is, edit the following variables which hold the paths to the demultiplex decode and fastq files as well as the READ1 & READ2 file extensions used:
```
#populate variables
DMXfiles=*_demultiplex.txt
FQfiles=*_1.fq.gz
R1Ext=_1.fq.gz
R2Ext=_2.fq.gz
```
