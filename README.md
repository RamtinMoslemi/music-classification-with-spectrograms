# music-classification-with-spectrograms
Music Classification using Spectrograms and Convolutional Neural Networks

### Source
This was one of the Computer Vision projects in Neuromatch Academy's Deep Learning course. You can find the original notebook [here](https://deeplearning.neuromatch.io/projects/ComputerVision/spectrogram_analysis.html).

### Dataset
The dataset used for this project, is the GTZAN dataset for music genre classification, which is available on [Kaggle](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification). This dataset consists of 10 genres of music with 100 audio files each, all having a length of 30 seconds. You can find the original audio files, the spectrograms (the visual representations) of the audio files, and 2 CSV files with extracted features on [Kaggle](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification). The spectrograms in this dataset are each made from one 30 second audio file, and if you need spectrograms made from each 3 second segment of the audio files, you can find them on my [google drive](https://drive.google.com/drive/folders/1tXOtfsoOn88uaKZIomjtZFC3mtx4qo0d) or you can make them yourself using [librosa](https://librosa.org/) as I did. Since it takes around 15 minutes to create either the mel scaled or the decibel scaled spectrograms, feel free to use the datasets that I made and save yourself 30 minutes by downloading (~3GB dataset) or by following these simple instructions:
1. Open this [link](https://drive.google.com/drive/folders/1tXOtfsoOn88uaKZIomjtZFC3mtx4qo0d) in your browser
2. Click on '3sec' then go to 'Organize' and create a shorcut on your drive using 'Add shortcut'
3. Now you can run the following command in the notebook to mount your drive and access the datasets:
   ```
   from google.colab import drive
   drive.mount('/content/drive')
   ```
   


