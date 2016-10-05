# Offline Voice Assistant using Snowboy Hotword Detection

by [KITT.AI](http://kitt.ai).

## Usage

python demo.py resources/model.pmdl resources/model2.pmdl ...

## Quick Start for Python Demo

Go to the `examples/Python` folder and open your python console:

    In [1]: import snowboydecoder

    In [2]: def detected_callback():
       ....:     print "hotword detected"
       ....:

    In [3]: detector = snowboydecoder.HotwordDetector("resources/snowboy.umdl", sensitivity=0.5, audio_gain=1)

    In [4]: detector.start(detected_callback)

Then speak "snowboy" to your microphone to see whetheer Snowboy detects you.

The `snowboy.umdl` file is a "universal" model that detect different people speaking "snowboy". If you want other hotwords, please go to [snowboy.kitt.ai](https://snowboy.kitt.ai) to record, train and downloand your own personal model (a `.pmdl` file).

When `sensitiviy` is higher, the hotword gets more easily triggered. But you might get more false alarms.

`audio_gain` controls whether to increase (>1) or decrease (<1) input volume.

Two demo files `demo.py` and `demo2.py` are provided to show more usages.

Note: if you see the following error:

    TypeError: __init__() got an unexpected keyword argument 'model_str'

You are probably using an old version of SWIG. Please upgrade. We have tested with SWIG version 3.0.7 and 3.0.8.
