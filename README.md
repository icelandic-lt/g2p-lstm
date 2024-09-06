LSTM encoder-decoder sequence-to-sequence models for Icelandic
==============================================================

This directory contains an LSTM encoder-decoder sequence-to-sequence models,
trained for Icelandic g2p. The models were trained using the baseline for the 
Sigmorphon 2020 Shared task in multilingual g2p, with manually transcribed training data of
~5,800 words per pronunciation variant.

Original Sigmorphon repository, from which the training scripts are copied: https://github.com/sigmorphon/2020/tree/master/task1

Reference paper: Gorman, Kyle et al. (2020): The SIGMORPHON 2020 Shared Task on Multilingual Grapheme-to-Phoneme Conversion.
In: Proceedings of the 17th SIGMORPHON Workshop on Computational Research in Phonetics, Phonology, and Morphology
(https://www.aclweb.org/anthology/2020.sigmorphon-1.2/)


## Fairseq setup

1. With Conda:

[`conda`](https://docs.conda.io/projects/conda/en/latest/user-guide/install/download.html)
is recommended for a reproducible environment. Once you have conda installed,
create a new conda environment by running this:

``` {.bash}
conda env create -f environment.yml
```

The new environment is called "fairseq-lstm". Activate it by running this:

``` {.bash}
conda activate fairseq-lstm
```

2. Clone Fairseq and install, see: https://github.com/pytorch/fairseq

## Training and executing

This repository contains trained models which you can use to automatically transcribe Icelandic words.
To train your own models, set up the ``data`` directory as in this example, including ``dev, test`` and ``train``
sub-directories.

With an activated fairseq-lstm environment, as described above, run the following to prepare the data
and train the model:

```
(fairseq-lstm) g2p-lstm % ./preprocess
(fairseq-lstm) g2p-lstm % ./sweep-is
```

To generate phonetic transcripts of words from a file containing a list of words, run the corresponding transcribe-script,
for icelandic-standard for example run ``transcribe_ice_standard``. Note that the characters in the words to transcribe
have to be space separated, e.g. ``h l a u p a``. The first argument (filename.out) contains predictions and prediction
values, the second one (filename.tsv) contains a tab-separated list of words and transcripts.

```
(fairseq-lstm) g2p-lstm % cat wordlist.txt | ./transcribe_ice_standard wordlist_g2p_standard.out wordlist_g2p_standard.tsv
```

## Use in g2p Python modules

For an example of how the models can be used in Python projects, see [ice-g2p](https://github.com/icelandic-lt/ice-g2p)

## Trouble shooting & inquiries

This application is still in development. If you encounter any errors, feel free to open an issue inside the
[issue tracker](https://github.com/grammatek/g2p-lstm/issues). You can also [contact us](mailto:info@grammatek.com) via email.

## Contributing

You can contribute to this project by forking it, creating a private branch and opening a new
 [pull request](https://github.com/grammatek/g2p-lstm/pulls).