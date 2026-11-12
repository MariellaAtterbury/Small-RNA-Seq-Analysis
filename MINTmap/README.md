# MINTmap Setup

MINTmap requires Java v1.8 (or greater) and Perl v5 (or greater)

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


Add reference files to a MINTmap directory created in the appropriate area. Reference files (can all be sourced from https://github.com/TJU-CMC-Org/MINTmap):
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
wget https://github.com/TJU-CMC-Org/MINTmap/tree/release/v1.0/MINTplates
```

