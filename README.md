# Rugby-Sequence-Data
Dataset for the  paper "Supervised sequential pattern mining of event sequences in sport to identify important patterns of play: an application to rugby union"
Preprint: https://arxiv.org/abs/2010.15377v1

This dataset can be split into four datasets: scoring, conceding, scoring+1 and conceding+1, based on the processes described in the paper and in the following diagram:
![image](https://user-images.githubusercontent.com/29388472/118747586-4019c280-b895-11eb-9fca-d35956407c17.png)

The results can be replicated using the SPP commands (https://github.com/takeuchi-lab/S3P-classifier):
./runspp.exe -L 20 -c 1 -M 1 -F ./output/[SCORING_OUTPUT_FILE]  ./data/scoring.txt and ./runspp.exe -L 20 -c 1 -M 1 -F ./output/[CONCEDING_OUTPUT_FILE]  ./data/conceding.txt, where the options -c 1 -M 1 mean that cross-validation is being used, and -L is the maximum pattern length.

The unsupervised models were applied using SPMF (https://www.philippe-fournier-viger.com/spmf/).
