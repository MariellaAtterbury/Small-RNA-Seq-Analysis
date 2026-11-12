# MINTmap Setup

#### MINTmap requires Java v1.8 (or greater) and Perl v5 (or greater)

Recommended to setup and install via conda environment:

``` 
conda create -n mintmap -c conda-forge -c bioconda mintmap
```

Activate the environment
```
conda activate mintmap
```
To confirm MINTmap has been installed correctly and view the parameters run
```
MINTmap.pl -h
```


#### Create a directory to store the MINTmap reference files. Reference files (can all be sourced from https://github.com/TJU-CMC-Org/MINTmap):
1. Lookup Table:
```
wget https://github.com/TJU-CMC-Org/MINTmap/blob/release/v1.0/LookupTable.tRFs.MINTmap_v1.txt
```

2. tRNA Sequences:
```
wget https://github.com/TJU-CMC-Org/MINTmap/blob/release/v1.0/tRNAspace.Spliced.Sequences.MINTmap_v1.fa
```

3. tRF Types:
```
wget https://github.com/TJU-CMC-Org/MINTmap/blob/release/v1.0/OtherAnnotations.MINTmap_v1.txt
```

4. MINTplates Path (used to create "tRF license-plates"):
```
git clone https://github.com/TJU-CMC-Org/MINTmap/tree/release/v1.0/MINTplates
```
# MINTmap Guide

Ensure directories used and reference files are set to correct file paths 
```
result_dir="path/to/results/directory"
fastq_dir="path/to/trimmed/directory"
lookuptable="path/to/LookupTable.tRFs.MINTmap_v1.txt"
tRNAsequences="path/to/tRNAspace.Spliced.Sequences.MINTmap_v1.fa"
tRFtypes="path/to/OtherAnnotations.MINTmap_v1.txt"
MINTplatesPath="path/to/MINTplates"
```

Depending on number of files, run the mintmap.sh or mintmap.slurm.array.sh script
```
sbatch mintmap.slurm.array.sh
```

Merge processed files using the merge script.

```
Rscript mintmap.merge.results.R <result_dir> <output_prefix>
```
This will produce five output files: 
```
<output_prefix>.mintmap.results.csv
<output_prefix>.ambiguous.tRFs.count.txt
<output_prefix>.exclusive.tRFs.count.txt
<output_prefix>.ambiguous.tRFs.metadata.csv
<output_prefix>.exclusive.tRFs.metadata.csv
```

These files contain a summary of the MINTmap result files that were found and merged, count matrices for ambiguous and exclusive tRFs, and the corresponding metadata files.

