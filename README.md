# Rugby-Sequence-Data
Dataset for the  paper "Supervised sequential pattern mining of event sequences in sport to identify important patterns of play: an application to rugby union"
Preprint: https://arxiv.org/abs/2010.15377v1

## Abstract
Given a set of sequences comprised of time-ordered events, sequential pattern mining is useful to identify frequent subsequences from different sequences or within the same sequence. However, in sport, these techniques cannot determine the importance of particular patterns of play to good or bad outcomes, which is often of greater interest to coaches and performance analysts. In this study, we apply a recently proposed supervised sequential pattern mining algorithm called safe pattern pruning (SPP) to 490 labelled event sequences representing passages of play from one rugby team's matches from the 2018 Japan Top League. We compare the SPP-obtained patterns that are the most discriminative between scoring and non-scoring outcomes from both the team's and opposition teams' perspectives, with the most frequent patterns obtained with well-known unsupervised sequential pattern mining algorithms when applied to subsets of the original dataset, split on the label. Our obtained results found that linebreaks, successful lineouts, regained kicks in play, repeated phase-breakdown play, and failed exit plays by the opposition team were identified as as the patterns that discriminated most between the team scoring and not scoring. Opposition team linebreaks, errors made by the team, opposition team lineouts, and repeated phase-breakdown play by the opposition team were identified as the patterns that discriminated most between the opposition team scoring and not scoring. It was also found that, by virtue of its supervised nature as well as its pruning and safe-screening properties, SPP obtained a greater variety of generally more sophisticated patterns than the unsupervised models, which are likely to be of more utility to coaches and performance analysts.

## Datasets
The dataset provided can be split into four datasets: scoring, conceding, scoring+1 and conceding+1, based on the processes described in the paper and in the following diagram:
![image](https://user-images.githubusercontent.com/29388472/118747586-4019c280-b895-11eb-9fca-d35956407c17.png)

## Applying the methods
### Applying SPP
The results can be replicated using the SPP commands (https://github.com/takeuchi-lab/S3P-classifier): \
```./runspp.exe -L 20 -c 1 -M 1 -F ./output/[SCORING_OUTPUT_FILE] ./data/scoring.txt```\
and\
```./runspp.exe -L 20 -c 1 -M 1 -F ./output/[CONCEDING_OUTPUT_FILE]  ./data/conceding.txt```\
where [SCORING_OUTPUT_FILE] and [CONCEDING_OUTPUT_FILE] are text file names for the output files that you specify, and the options -c 1 -M 1 mean that cross-validation is being used, and -L is the maximum pattern length.

### Applying the unsupervised methods
The unsupervised models were applied using SPMF (https://www.philippe-fournier-viger.com/spmf/).
Note that the required data format for SPMF differs to SPP.
