# Tacotron2-Text-to-Speech-model
**TTS Training with Tacotron2**

This repository contains a script for training a Tacotron2 Text-to-Speech (TTS) model using the LJSpeech dataset on Google Colab. The Tacotron2 model is a popular architecture for end-to-end TTS synthesis.

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

**4. Citations**
- https://github.com/justinjohn0306/FakeYou-Tacotron2-Notebook
