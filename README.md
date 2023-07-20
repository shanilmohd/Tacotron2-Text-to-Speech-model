# Tacotron2-Text-to-Speech-model
**TTS Training with Tacotron2**

This repository contains a script for training a Tacotron2 Text-to-Speech (TTS) model using the LJSpeech dataset on Google Colab. The Tacotron2 model is a popular architecture for end-to-end TTS synthesis.

Colab Notebook link: https://githubtocolab.com/shanilmohd/Tacotron2-Text-to-Speech-model/blob/main/Tacotron_2_TTS.ipynb

**Note: This training script is designed for Google Colab, and it assumes you have access to a GPU.**

**1. Dataset Preparation**
Before running the training script, you need to prepare the LJSpeech dataset. The dataset should be organized in the following directory structure:

```
- wavs/
    -1.wav
    - 2.wav
    - ...

```

The `wavs` directory should contain the audio files in WAV format, and the `filelists` directory should have text file: `list.txt`. These text files should list the audio file paths and corresponding text transcriptions, separated by the '|' character. For example:

```
wavs/1.wav|He bought a saw, a tape measure, and a few other tools from the store.
wavs/2.wav|The sun was setting and the sky was turning red.
...
```

Ensure that you have the necessary permissions to access and modify the data directory.

**2. Training Configuration**
In the script, you may need to adjust the following variables based on your specific setup:

- `output_directory`: The directory to save model checkpoints.
- `log_directory`: The directory to save tensorboard logs locally.
- `log_directory2`: The directory to copy log files (optional).
- `checkpoint_path`: The path to save model checkpoints.
- `hparams.training_files`: Set this variable to the path of the `clipper_train_filelist.txt`.
- `hparams.validation_files`: Set this variable to the path of the `clipper_val_filelist.txt`.

**3. Running the Training Script**
Once the dataset is properly organized, you can start the TTS model training by running the provided script in Google Colab. The script will handle the training process, including downloading necessary requirements, initializing the model, and performing the main training loop.

During the training process, the model's performance will be logged, and validation will be performed after each epoch to assess the model's quality.

**4. Additional Notes**
- Training a TTS model can be computationally intensive and may require a significant amount of time and resources, especially if training for many epochs.
- If you encounter issues related to GPU memory, you may need to adjust the batch size or use a smaller model.
- Always ensure you have access to sufficient GPU memory and runtime availability on Google Colab.
- If you plan to run long training sessions, consider setting up the `log_directory2` variable to copy log files to a backup location.

**5. Running the model**
- Run the code snippet in google colab which has a comment "Run this code segment for using the trained model".
- It will ask for a text input and it will create a speech output in the trained voice.

**6. Dataset**
 - https://www.kaggle.com/datasets/mathurinache/the-lj-speech-dataset
 - This is a public domain speech dataset consisting of 13,100 short audio clips of a single speaker reading passages from 7 non-fiction books. A transcription    is provided for each clip. Clips vary in length from 1 to 10 seconds and have a total length of approximately 24 hours.
 - The texts were published between 1884 and 1964, and are in the public domain. The audio was recorded in 2016-17 by the LibriVox project and is also in the      public domain.
   
**7. Training**
 - Training is done on 100 audio samples from dataset
 - Validations loss reported after 215 epochs is 0.119743
 
**8. Citations**
- https://github.com/justinjohn0306/FakeYou-Tacotron2-Notebook
