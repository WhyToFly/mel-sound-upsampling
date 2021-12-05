# mel-sound-upsampling
## Code for my final project "GAN Mel Spectrogram Upscaling for Audio Super-Resolution" for [cs395T - Deep Learning Seminar with Philipp Krähenbühl](https://www.philkr.net/cs395t)

Contains a modified version of [BasicSR/ESRGAN](https://github.com/xinntao/BasicSR) and an iPython notebook to generate data.

Usage: 
* Extract [VCTK Dataset](https://datashare.ed.ac.uk/handle/10283/3443), adjust file path in notebook and generate data
* copy data to BasicSR/datasets/multispeaker
* modify BasicSR/options/train/ESRGAN/train_ESRGAN_MEL.yml/BasicSR/options/test/ESRGAN/test_ESRGAN_MEL.yml
* train using `python basicsr/train.py -opt options/train/ESRGAN/train_ESRGAN_MEL.yml`
* during training, you can listen to validataion outputs (follow code in notebook)
* batch generate upscaled audio files by putting 11025Hz files into BasicSR/inference_data and running `python basicsr/inference.py -opt options/test/ESRGAN/test_ESRGAN_MEL.yml`

The `samples` directory contains audio samples randomly chosen from the test data. "\_low\_sr" files are the 11025Hz inputs to the model, "\_label" files are the 44100Hz labels and "\_pred" files are the network's predictions.
