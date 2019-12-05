# Explain Pensieve (SIGCOMM'17)

## Prerequisites
### Dependencies
Install required dependencies:

``
pip install python==3.7.4 numpy==1.17.2 tensorflow==1.14.0 tflearn==0.3.2 scikit-learn==0.21.3 pydotplus==2.0.2
``
Tips: If you are facing the problem `illegal instruction` when import tensorflow, you may refer to articles:[[1](https://tech.amikelive.com/node-882/how-to-build-and-install-the-latest-tensorflow-without-cuda-gpu-and-with-optimized-cpu-performance-on-ubuntu/)] or [[2](https://github.com/naruai/wiki/blob/master/TensorFlow/BuildTensorFlowWOAVX.md)]. Also, the easiest way to deal with it is to use `tensorflow==1.5.0` instead of `tensorflow==1.14.0`.
### Traces
Unzip the cooked traces:

``
unzip cooked_traces.zip
``

Traces are originally from the `cooked_test_traces` at https://www.dropbox.com/sh/ss0zs1lc4cklu3u/AAB-8WC3cHD4PTtYT0E4M19Ja, which was compiled by the authors of Pensieve.

### Video
We provide the video information in `video/`, where each file records the chunk size at different (six) bitrates. Put your video manifests there.

### DNN Model
We provide the pre-trained DNN model at `models/pretrain_linear_reward.ckpt`. You can follow the instructions in the original Pensieve repository to train your own DNN model.
If you would like to use your own DNN model, you can modify `model_path` in `main.py` #L28. 

## Generate a decision tree with given data traces 

```
mkdir decision_tree
python main.py 100
```

The decision tree could be found in `decision_tree` in the format of `.svg`.
