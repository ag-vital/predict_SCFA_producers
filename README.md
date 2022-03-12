## predict_SCFA_producers

1. the folder *UHGG_references* contain reference sequences of pathways from UHGG genomes screening.

2. the folder *picrust_files* contains all files for using picrust.
  * reference tree (SCFA.tre)
  * alignment of reference sequences (SCFA.fasta)
  * HMM based on reference sequences (SCFA.hmm)
  * RaXmL model file (SCFA.model)
  * feature file (SCFA_pathwaydata.txt)

#### instructions for picrust

install picrust2:\
https://github.com/picrust/picrust2/wiki

insert your ASVs into the reference tree:\
place_seqs.py -s {your sequence fasta file}  -o placed_seqs.tre -p 1 --intermediate placement_working --ref_dir {path to SCFA files}

Hidden-state prediction:\
hsp.py -t placed_seqs.tre --observed_trait_table {path to SCFA files} -o SCFA_predicted.tsv -p 1 -m emp_prob -n
