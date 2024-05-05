# music-classification-with-spectrograms
Music Classification using Spectrograms and Convolutional Neural Networks


### Source
This was one of the Computer Vision projects in Neuromatch Academy's Deep Learning course. You can find the original notebook [here](https://deeplearning.neuromatch.io/projects/ComputerVision/spectrogram_analysis.html) and the instruction slide which goes through the background, project setup, and project map [here](https://github.com/RamtinMoslemi/music-classification-with-spectrograms/blob/main/spectrogram_analysis.pdf); Both of these resources where provided by Neuromatch Academy. My work was heavily inspired by the original notebook and steps involving the creation of spectrograms were especially helpful, the project map provided in the instruction slide was very insightful and served as a source of inspiration for utilizing many methods which played a crucial role in achieving better results.

### Dataset
The dataset used for this project, is the GTZAN dataset for music genre classification, which is available on [Kaggle](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification). This dataset consists of 10 genres of music with 100 audio files each, all having a length of 30 seconds. You can find the original audio files, the spectrograms (the visual representations) of the audio files, and 2 CSV files with extracted features on [Kaggle](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification). The spectrograms in this dataset are each made from one 30 second audio file, and if you need spectrograms made from each 3 second segment of the audio files, you can find them on my [google drive](https://drive.google.com/drive/folders/1tXOtfsoOn88uaKZIomjtZFC3mtx4qo0d) or you can make them yourself using [librosa](https://librosa.org/) as I did. Since it takes around 15 minutes to create either the mel scaled or the decibel scaled spectrograms, feel free to use the datasets that I made and save yourself 30 minutes by downloading (~3GB dataset) or by following these simple instructions:
1. Open this [link](https://drive.google.com/drive/folders/1tXOtfsoOn88uaKZIomjtZFC3mtx4qo0d) in your browser
2. Click on '3sec' then go to 'Organize' and create a shorcut on your drive using 'Add shortcut'
3. Now you can run the following command your the notebook to mount your drive and access the datasets:
```
from google.colab import drive
drive.mount('/content/drive')
```
   
### Methods
The main purpose of this project was to use convolutional neural networks to perform music genre classification. In addition to simply training a CNN, I used Transfer Learning as suggested in the project map and used some pretrained models such as ResNet. Furthermore I used XGBoost on the CSV files containing extracted features to compare the results to  the CNNs and observe the difference in these approaches.


### Results
| Model | Pre-Training | Dataset | Spectrogram Scale | Accuracy |
| :---: | :---: | :---: | :---: | :---: | 
| CNN | no | 30 second | mel scale | 66% |
| ResNet18 | no | 30 second | mel scale | 71% |
| ResNet18 | no | 3 second + MV | decibel scale | 75% |
| ResNet18 | no | 3 second + Prob | decibel scale | 77% |
| ResNet18 | yes | 30 second | mel scale | 77% |
| ResNet18 | yes | 3 second + MV | mel scale | 83% |
| ResNet18 | yes | 3 second + Prob | mel scale | 85% |
| ResNet18 | yes | 3 second + MV | decibel scale | 90% |
| ResNet18 | yes | 3 second + Prob | decibel scale | 89% |
| XGBoost | - | 30 second | - | 74%|
| XGBoost | - | 3 second | - | 90.4%|
| XGBoost | - | 3 second + MV | - | %|

![Unknown](https://github.com/RamtinMoslemi/music-classification-with-spectrograms/assets/76493699/dc85ac21-7c1e-4bcc-bc1c-4d8840922fe1)

