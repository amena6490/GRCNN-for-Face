# GRCNN-for-Face
Gated Recurrent Convolution Neural network for Face Recognition with Combined Angular Loss
The network architecture uses GRCNN and we implements a combined angular margin softmax loss function for face recognition. This code is built upon david's facenet and tested on Tensorflow = 1.4.0

# GRCNN:
This project is an application of GRCNN for face recognition. For details of GRCNN architecture, please refer to the paper: https://papers.nips.cc/paper/6637-gated-recurrent-convolution-neural-network-for-ocr.pdf

# Combined Augular Softmax Loss：
The combined augular softmax introduces the augular margin in cosine theta and adds substract another margin outside the cosine theta.
The combined angular softmax can be written as:

<div align=center><img src="https://github.com/Jianfeng1991/GRCNN-for-Face/blob/master/combined_loss.PNG" width="450" height="120" ></div>

where the s denotes scale factor, m1 and m2 are angular marigin and n is the number of images in a single batch.

# Train a new model
1. Preparing for the datasets: 
All of images for a identity should put in one directory, and the images should be preprocessed by MTCNN. The preprocessing script can be found at process_data.sh.

2. Run the training script:
The training settings are written in train_mscele_vgg_combined.sh. The training datasets we use is a combination of MsCele and VGG datasets which are cleaned by ouselves.

# Inference
In this experiment, we only use MTCNN for face detection and we do not perform face alignment.
We evaluate GRCNN on lfw datasets and it achieve 99.82 % accuracy. The pre-trained model will be relased soon.

# references

1. https://papers.nips.cc/paper/6637-gated-recurrent-convolution-neural-network-for-ocr.pdf

2. https://arxiv.org/abs/1801.05599  (Additive Margin Softmax for Face Verification)

3. https://arxiv.org/abs/1801.07698  (ArcFace: Additive Angular Margin Loss for Deep Face Recognition)
