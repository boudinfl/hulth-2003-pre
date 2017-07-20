# Preprocessed Inspec keyphrase extraction benchmark dataset

This dataset was introduced in:

 - **Improved automatic keyword extraction given more linguistic knowledge**
   Anette Hulth.
   *In Proceedings of EMNLP 2003.*
   p. 216-223.

The dataset is split into four directories:

  * `references`: reference keyphrases for evaluation
  * `test`: test set
  * `train`: training set
  * `dev`: validation set
  * `src`: scripts and archive from which the dataset is built

Each input file is processed using the Stanford CoreNLP suite v3.6.0.
We use the default parameters and perform tokenization, sentence splitting and
Part-Of-Speech (POS) tagging. Files are in XML format.

Reference keyphrases are in json format and named according to the following
rules:

    [test|train].[uncontr|contr].[stem]?.json

controlled (contr) or uncontrolled (uncontr) indexer-provided (stemmed or not) 
reference keyphrases for test, train and dev splits.

Stemming (if applied), is performed with nltk Porter algorithm (English).

Below is a toy example of reference file:

    {
        "doc-1": [
            [
                "target detect"
            ],
            [
                "number of sensor",
                "sensor number"
            ]
        ],
        ...
    }