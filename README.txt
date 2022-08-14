These Colab Notebooks include the source code to recreate the models in my dissertation.
Before starting you need to download the CoughVID dataset from
https://zenodo.org/record/4498364#.YvkdwXbMKUk
Store on your Google Drive in a folder called
/Colab Notebooks/coughvid/public_dataset

The following 2 Colab Notebooks will clone the relevant GitHubs for Virufy and Coswara data and extract the audio files and metadata to your Google Drive:

Download_coswara_data.ipynb
Download_Virufy_data.ipynb
Since downloading for my dissertation the GitHub I cloned for Virufy has been removed. If it has not reappeared try cloning this GitHub instead:
https://github.com/Alja9/virufy-cdf-india-clinical-1

The following 3 notebooks create a pandas dataframe containing the metadata and a path to each audio file for each source.
Coswara_dataframe.ipynb
CoughVID_dataframe.ipynb
Virufy_dataframe.ipynb

The following 3 notebooks create Mel Spectrograms from the audio files and add a path to the image file to the pandas dataframes created in previous notebooks:
Create_Coswara_images.ipynb
Create_CoughVID_images.ipynb
Create_Virufy_images.ipynb

The following notebook combines the pandas dataframes for all 3 sources into 1 called combined_dataset.csv and creates pandas dataframes df_healthy.csv and df_covid.csv. These 3 files are available on the repository so running this notebook can be skipped and the files stored on the repository used instead.
Dataset_dataframe.ipynb

The following notebook splits out a test set so that all methods are tested on the same unseen data. My sets are available on the repository. They are df_train.csv and df_test.csv so running this notebook can be skipped and these files used instead.
Create_a_test_set.ipynb
These notebooks test the different methods to combat class imbalance in the datasets:
Detecting_COVID_CNN_bias_initializer.ipynb
Detecting_COVID_CNN_threshold_moving.ipynb
Detecting_COVID_CNN_class_weights_generator.ipynb
Detecting_COVID_CNN_oversampling.ipynb
Detecting_COVID_CNN_Undersampling.ipynb
Detecting_COVID_CNN_Mixed.ipynb

These notebooks investigated structures from other author’s papers:
Andreu_Perez_ Detecting_COVID_CNN_oversampling.ipynb
Dunne_ Detecting_COVID_CNN_oversampling.ipynb
Imran_ Detecting_COVID_CNN_oversampling.ipynb
Zhou_ Detecting_COVID_CNN_oversampling.ipynb

This notebook uses transfer learning from a pretrained models. Simply change the pretrained model in the code for different pretrained models. 
Pretrained_Detecting_COVID_CNN_oversampling.ipynb

This notebook finetunes the best CNN model on Mel Spectrograms:
Detecting_COVID_CNN_mel_spectograms.ipynb

This notebook extracted MFCCs from audio recordings:
Extract_rawMFCCs.ipynb

These notebooks investigated CNNs and LSTMS on MFCCs (Previous notebook Extract_rawMFCCs.ipynb  needs to be run first):
mfccs_CNN.ipynb
mfccs_CNN_oversampling.ipynb
mfccs_RNN_LSTM.ipynb
mfccs_RNN_LSTM_oversampling.ipynb
mfccs_RNN_LSTM_oversampling_bidirectional.ipynb
mfccs_RNN_LSTM_oversampling_multilayer.ipynb

These notebooks extracted mean values for MFCCs and applied the Random Forest Algorithm (they must be run in order):
Extraction_of_mean_rawMFCCs.ipynb 
Create_Dataframe_rawMFCCs.ipynb 
COVID Random Forest with Oversampling.ipynb

The following notebooks were used to test the impact of age and gender:
COVID_CNN_different_ages.ipynb
Detecting_COVID_CNN_Gender.ipynb
Detecting_COVID_CNN_age.ipynb

The following pandas dataframes are available on the repository to assist in reproducing my models.
combined_dataset.csv
df_test.csv
df_train.csv
df_healthy.csv
df_covid.csv
