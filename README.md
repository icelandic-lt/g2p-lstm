LSTM encoder-decoder sequence-to-sequence models for Icelandic
==============================================================

This directory contains an LSTM encoder-decoder sequence-to-sequence models,
trained for Icelandic g2p. The models were trained using the baseline for the 
Sigmorphon 2020 Shared task in multilingual g2p, with manually transcribed training data of
~5,800 words per pronunciation variant.

See code for training and evaluation: https://github.com/sigmorphon/2020/tree/master/task1

Reference paper: Gorman, Kyle et al. (2020): The SIGMORPHON 2020 Shared Task on Multilingual Grapheme-to-Phoneme Conversion.
In: Proceedings of the 17th SIGMORPHON Workshop on Computational Research in Phonetics, Phonology, and Morphology
(https://www.aclweb.org/anthology/2020.sigmorphon-1.2/)


Fairseq setup
==============

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


## Trouble shooting & inquiries

This application is still in development. If you encounter any errors, feel free to open an issue inside the
[issue tracker](https://github.com/grammatek/g2p-lstm/issues). You can also [contact us](mailto:info@grammatek.com) via email.

## Contributing

You can contribute to this project by forking it, creating a private branch and opening a new
 [pull request](https://github.com/grammatek/g2p-lstm/pulls).