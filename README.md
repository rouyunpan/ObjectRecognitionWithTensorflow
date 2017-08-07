# ObjectRecognitionWithTensorflow


1.validate_alexnet_on_imagenet.ipynb
1-1.validate the alexnet model, please download bvlc_alexnet.npy from http://www.cs.toronto.edu/~guerzhoy/tf_alexnet/
put the pre-train weight "bvlc_alexnet.npy" in current folder.

1-2 excute "validate_alexnet_on_imagenet.ipynb" on jupyter notebook


2.image_process.py
2-1. please download new dataset "train.zip" and upzip in ./data 
https://www.kaggle.com/c/dogs-vs-cats/data
2-2. to generate the index for new dataset
- arg1 : the location for train image
- arg2: the path for generating the index "tain.txt" 和 val.txt 
- arg3 the ratio for training
Usage: $python image_process.py ./data/train ./data 0.8

train.txt：
/home/tensorflow/Projects/Tensorflow/ObjectRecognitionWithTensorflow/data/train/dog.9528.jpg 1
/home/tensorflow/Projects/Tensorflow/ObjectRecognitionWithTensorflow/train/cat.9138.jpg 0
/home/tensorflow/Projects/Tensorflow/ObjectRecognitionWithTensorflow/data/train/cat.2848.jpg 0

3.fintune.py
3-1 create the fodler for re-train model and tensorboard in "./data/checkpoints" and "./data/filewriter".
3-2 $python fintune.py
... 
2017-08-07 14:49:25.013917 Start training...
2017-08-07 14:49:25.014005 Open Tensorboard at --logdir ./data/filewriter
2017-08-07 14:49:25.014036 Epoch number: 1
2017-08-07 15:08:24.928131 Start validation
2017-08-07 15:10:39.687864 Validation Accuracy = 0.9548
2017-08-07 15:10:39.687961 Saving checkpoint of model...
2017-08-07 15:10:40.314690 Model checkpoint saved at ./data/checkpoints/model_epoch1.ckpt
2017-08-07 15:10:40.314793 Epoch number: 2
...

4. validate_alexnet_after_fintune.ipynb
4-2 put new test images in ./input_images_1
4-1 excuting "validate_alexnet_after_fintune.ipynb" on jupyter notebook, and checking the result for new dataset
