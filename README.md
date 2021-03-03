# Halogenase
This repository provides the profile hidden Markov model for flavin-dependent tryptophan halogenase (Trp-FDH) and Python script for filtering result of pHMM search.

## Pre-installed programs
* Python version 2.7.12 or higher
* HMMER3.0 package version 3.1b2 or higher

## Filtering result of pHMM search
### Step 1: pHMM search
To perform the pHMM search, *hmmscan* in HMMER3.0 package is used with "--domtblout" option.   
A query should be included as protein sequences in the FASTA format file.   
Usage:   
```
hmmscan --domtblout output.domtblout Trp_FDH.hmm query.fasta
```

### Step 2: filtering .domtblout file
To filter the .domtblout file, ```domtblout_filtering.py``` is used.

