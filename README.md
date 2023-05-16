# Objective evaluation of audio quality

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

This repository contains the project materials for the objective evaluation and comparison between objective and subjective evaluation techniques. The project focuses on the lecture delivered by ReadSpeaker during the Summer School of 2023. The goal of this study is to examine the effectiveness of objective evaluation methods in contrast to subjective evaluation approaches. The repository includes code and sample data related to the project. Through this comparative study, we aim to gain insights into the strengths and limitations of each evaluation method and contribute to the field of speech technology assessment.

This project is developed and tested in google colab environment. Please build up the python environment properly in advance, if you want to run it in other different environment.

## Table of Contents

- [Usage](#usage)
- [Contact](#contact)

## Data preparation

You could find one pair of audio samples under then samples folder. They could be used to calculated the score for different metrics. If you would like to evaluate the degraded and resynthesized audios like we did on the lecture, please add you own parallel audios into the data folder with the data structure as below. Please notice: the "long" or "short" in filenames represent the type of audio length. It's used to make comparison the result difference between long and short audios. If you don't mean to do so, please just name them like. wav_001.wav, wav_002.wav, wav_003.wav ....

```
data
├── samples
├── degraded
|   ├── wav_001_long.wav
|   ├── wav_001_short.wav
|   ├── wav_002_long.wav
|   └── ...
├── raw
|   ├──wav_001_long.wav
|   ├── wav_001_short.wav
|   ├── wav_002_long.wav
|   └── ...
└── resyn
    ├── wav_001_long.wav
    ├── wav_001_short.wav
    ├── wav_002_long.wav
    └── ...
```


## Clone other repos

There are three machine learning based models used in this project. [MOSNet](https://github.com/lochenchou/MOSNet), [VISQOL](https://github.com/google/visqol), [NISQA](https://github.com/gabrielmittag/NISQA) 

Please clone them from github in advance. Please run the following code in your notebook.

```
$git clone https://github.com/lochenchou/MOSNet.git
$git clone https://github.com/google/visqol.git
$git clone https://github.com/gabrielmittag/NISQA.git
```

Please notice, it takes a very long time to build up visqol in colab (~2 hours). You can follow the instructions in the notebook to build it or just skip those steps.

After all the installation and data collection, your folder should like as below.

``` 
├── MOSNet
├── visqol
├── NISQA
├── data
| ├── samples
| ├── degraded
| |   ├── wav_001_long.wav
| |   ├── wav_001_short.wav
| |   ├── wav_002_long.wav
| |   └── ...
│ ├── raw
| |   ├──wav_001_long.wav
| |   ├── wav_001_short.wav
| |   ├── wav_002_long.wav
| |   └── ...
│ └── resyn
|     ├── wav_001_long.wav
|     ├── wav_001_short.wav
|     ├── wav_002_long.wav
|     └── ...
├── result
└── README.md
```

## Objective evaluation

In this part, you will calculate 9 different objective evaluation metrics, MCD, F0-FCC, PESQ, MOSNet, VISQOL,VDE, GPE, FFE and NISQA. 5 of them have be introduced in the lecture and the other 4 types of metrics also have detailed comments. Please do this by following the detailed instructions within objective_eval.ipynb step by step.

After running all the cells, there should be two csv files in result folder, summary_degraded.csv and summary_resyn.csv. They will be used for next step, result analysis.

## Result analysis

Please do this by following the detailed instructions within result_eval.ipynb step by step.

Notice: If you want to make comparison between subjective and objective evaluation, please do subjective evaluation in advance and calculate the average score of two different types of audios.

## Contact

Please contact me if you have any problem about it. <xiaoning.shi@readspeaker.com>
