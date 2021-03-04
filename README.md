# Halogenase
This repository provides the profile hidden Markov model (pHMM) for flavin-dependent tryptophan halogenase (Trp-FDH) and Python script for filtering result of pHMM search.

>## Pre-installed programs
* Python version 2.7.12 or higher
* HMMER3.0 package version 3.1b2 or higher

>## Filtering result of pHMM search
### pHMM search
  - To perform the pHMM search, *hmmscan* in HMMER3.0 package is used with "--domtblout" option.   
  - A query should be included as protein sequences in the FASTA format file.   
```
$ hmmscan --domtblout output_file_name.domtblout pHMM/Trp_FDH.hmm query.fasta
```

### Filtering .domtblout file
  - To filter the .domtblout file, ```code/domtblout_filtering.py``` is used.   
  - According to the threshold for e-value and pHMM model coverage, the search result is filtered.
```
$ python domtblout_filtering.py -i example/example_input.domtblout -o example/example_output.domtblout -e e-value -c model_coverage
```

>## Putative FDHs   
* Protein sequences of eleven putative FDHs (Hal1-7 and MHal1-4) are in ```/putative_FDHs```.

>## Halogenases on embedding space   
* The list of 313 halogenases used in embedding (t-SNE) are in ```/halogenases_on_embedding_space```.   
* Each file includes accession number, annotation, and source organism of halogenases.   

|File name|Description|# of halogenases|
|:----|:----|:----|
|1_known.csv|previously identified halogenases|33|
|2_keyword-search.csv|halogenases obtained from NCBI by keyword-search|109|
|3_inside_BGC.csv|halogenases inside BGC|20|
|4_outside_BGC.csv|halogenases outside BGC|83|
|5_metagenome.csv|halogenases from sediment microbiomes|68|
||Total|313|



