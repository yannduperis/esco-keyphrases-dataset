# A labor market keyphrase data set built from ESCO

Keyphrases are defined in classical _Information Retrieval_ as a sequence of one or more words that 
capture the main topics discussed in a document [1].

This repository contains a data set of keyphrases that can be extracted/generated from labor market documents (job 
offers, resumes, etc.). This data set has been extracted from the European Skills, Competences, Qualifications, 
and Occupations ontology - ESCO [2]. 

This ontology comprises a classification of _Occupations_ (3k concepts) and _Skills_
(14k concepts), linked by semantic relationships. Each occupation, or skill, _concept_ is associated with multiple 
alternative labels (with a varying number of alternative labels for each one of the 24 European languages).

To foster research work on keyphrase matching (training and evaluation), this repository contains concept labels
extracted in collections of labor market keyphrases and alternative labels modeled as positive relevance feedback 
between keyphrases.

# Structure

- language (en / fr / en_fr)
  - keyphrase type (occupation titles / skills)
    - reference (all) / evaluation (10% of qrels for keyphrase matching evaluation):
      - `labels.txt`: keyphrases collection, **ID is line number, starting at 0** ;
      - `qrels.json`: keyphrases matching queries with relevance feedback

```
# qrels.json
{
    [...]
    "$QUERY_KEYPHRASE_ID": [
        $MATCHING_KEYPHRASE_1_ID,
        $MATCHING_KEYPHRASE_2_ID,
        $MATCHING_KEYPHRASE_3_ID,
        $MATCHING_KEYPHRASE_4_ID,
        [...]
    ]
    [...]
}
```      

# Description

| **Data set**        | **Evaluation queries** | **Keyphrases collection size** |
|:-------------------:|:----------------------:|:------------------------------:|
| En (occupations)    | 3.3k                   | 33k                            |
| En (skills)         | 9.7k                   | 97k                            |
| Fr (occupations)    | 1.7k                   | 11k                            |
| Fr (skills)         | 0.7k                   | 4.6k                           |
| En/Fr (occupations) | 4.4k                   | 44k                            |
| En/Fr (skills)      | 11k                    | 114k                           |

Table 1: description of the content of the data set

# References
**1.** Turney, P.D.: _Learning algorithms for keyphrase extraction. Information Retrieval_
2, 303–336 (2004)

**2.** le Vrang, M., Papantoniou, A., Pauwels, E., Fannes, P., Vandensteen, D., Smedt,
J.D.: _Esco: Boosting job matching in europe with semantic interoperability_. Com-
puter 47, 57–64 (2014)