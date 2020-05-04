# Neural-Style-Transfer
Fast Image Stylization using Instance Normalization with Pytorch

## Start Training
<pre>
python src/style_transfer.py train 
      --dataset train 
      --style-image style/mosaic.jpg 
      --save-model-dir save 
      --model-name mosaic 
      --cuda 1
</pre>

Flag description :  

`--dataset` folder containing images for training  
`--style-image` style of image you want to use  
`--save-model-dir` name of the folder where the model will be stored  
`--model-name` name of the model to be saved with `.model` extensions  
`--cuda` set it to 1 for running in GPU and 0 for CPU  

There are several other flags that you can use :

`--epochs` number of training epoch, default is `2`  
`--batch-size` number of batch size for training, default is `4`  
`--pretrained-model` pre-trained model path with `.model` extensions, default is `None`  
`--checkpoint-model-dir` path to folder where checkpoints of trained models will be saved, default is `None`  
`--image-size` size of training image, default is `256 x 256`  
`--style-size` size of style-image, default is the `original size` of style-image  
`--seed` random seed for training, default `42`  
`--content-weight` weight for content-loss, default is `1e5`  
`--style-weight` weight for style-loss, default is `1e10`  
`--lr` learning rate, default is `1e-3`  
`--log-interval` number of images after which the training loss is logged, default is `500`  
`--checkpoint-interval` number of batches after which a checkpoint of the trained model will be created, default is `2000`  

## Evaluate
<pre>
python src/style_transfer.py eval 
      --content-image image.jpg 
      --output-image image_mosaic.jpg
      --model save/mosaic.model 
      --cuda 1
</pre>

Flag description :

`--content-image` path to content image you want to stylize  
`--output-image` path for saving the output image  
`--model` saved model to be used for styling the image  
`--cuda` set it to 1 for running in GPU and 0 for CPU

## Result
![Result](https://github.com/Malikanhar/Neural-Style-Transfer/raw/master/assets/result.png)
