# Target Type Identification for Entity-Bearing Queries

This repository provides resources developed within the following paper:

> D. Garigliotti, F. Hasibi and K. Balog. Target Type Identification for Entity-Bearing Queries, In SIGIR'17, August 2017.

These resources allow to reproduce the results presented in the Target Type Identification paper.

The repository is structured as follows:

- `data/qrels/`: CSV file with the test collection built from a crowdsourcing annotations; 
- `data/ml/`: CSV machine learning dataset with all the pre-computed features; 
- `lib/trec_eval/`: TREC evaluation file (see its Readme);
- `output/`:  all the final CSV run files, containing target types ranked by baseline methods and our proposed approach.


## Machine learning data

Each instance of this CSV dataset is structured as follows:

- The first and second columns correspond to the query and type;
- The third column is the target to predict;
- The rest of the columns corresponds to the 25 features, in the same order as presented in Table 1 of the paper.


## Results

Results presented in the paper can be obtained by running the TREC evaluation script as usual, indicating the metrics of interest.
E.g., placed on `sigir2017-query_types` directory, the following
```
$ ./lib/trec_eval.9.0/trec_eval -c -m ndcg_cut.1,5 data/qrels/qrels-tti-CF-filtered_by_NIL+merged.csv output/ltr/scores-tti-ltr-rf-n_1000-m_3.csv
```
evaluates our proposed Learning-to-rank method with the NDCG@1 and NDCG@5 metrics.


## Contact
Should you have any questions, please contact Darío Garigliotti at dario.garigliotti[AT]uis.no (with [AT] replaced by @).
