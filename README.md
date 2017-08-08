# darknet-mobilenet
The mobilenet model of Google's mobileNets in darknet framework. The official paper:
MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications

I provide a cfg file of mobilenet and a pretrained mobilenet weights on ImageNet. 

This model achieved top-1 accuracy 71.1% and top-5 accuracy 90.5% (image size:448x448)
 
Note:
You want to use this model in darknet, you must wirte a group conv layer.

mobilenet_yolo_coco:(approximationly 0.5:0.95mAP 16.2%)
链接: https://pan.baidu.com/s/1qXRFRlU 密码: 4qr8
mobilenet_yolo_voc:(According to loss value, I guess mAP 0.5mAP 65%-70%)
链接: https://pan.baidu.com/s/1qY4Vy9m 密码: qk4q

By visualing the weights of mobilenet, we found that some filters have a weight of zero. We compress the mobilenet with thresholds of 0.0001 and 0.08, respectively. So the model with thresholds 0.0001 achived the same accuracy as original mobilenet (top-1: 0.712540, top-5: 0.903520), and the other model with thresholds 0.08 achived accuracy with top-1 0.682580 and top-5 0.885100. All the compress model without finetune.

Update

Compress mobilenet with threshold of 0.1, then finetune it for 20 epochs, finally this network achived accuracy with top-1 0.697 and top-5 0.897, and the size of this model is 10.1M.
