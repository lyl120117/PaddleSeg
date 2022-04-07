# PP-LiteSeg: A Superior Real-Time Semantic Segmentation Model

## Reference

> todo

## Performance

### Cityscapes

| Model | Backbone | Training Iters | Train Resolution | Test Resolution | mIoU | mIoU (flip) | mIoU (ms+flip) | Links |
|-|-|-|-|-|-|-|-|-|
|PP-LiteSeg-T|STDC1|160000|1024x512|1025x512|73.10%|73.89%|-|[config](./pp_liteseg_stdc1_cityscapes_1024x512_scale0.5_160k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc1_cityscapes_1024x512_scale0.5_160k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc1_cityscapes_1024x512_scale0.5_160k/train.log)\|[vdl](https://www.paddlepaddle.org.cn/paddle/visualdl/service/app/scalar?id=66db3a2815980e41274ad587df2cd4e4)|
|PP-LiteSeg-T|STDC1|160000|1024x512|1536x768|76.03%|76.74%|-|[config](./pp_liteseg_stdc1_cityscapes_1024x512_scale0.75_160k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc1_cityscapes_1024x512_scale0.75_160k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc1_cityscapes_1024x512_scale0.75_160k/train.log)\|[vdl](https://www.paddlepaddle.org.cn/paddle/visualdl/service/app/scalar?id=ea5d56fbfceb8d020eabe46e9bc8c40c)|
|PP-LiteSeg-T|STDC1|160000|1024x512|2048x1024|77.04%|77.73%|77.46%|[config](./pp_liteseg_stdc1_cityscapes_1024x512_scale1.0_160k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc1_cityscapes_1024x512_scale1.0_160k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc1_cityscapes_1024x512_scale1.0_160k/train.log)\|[vdl](https://paddlepaddle.org.cn/paddle/visualdl/service/app?id=b9d2ca9445c5b3ee41db8ec37252d3e8)|
|PP-LiteSeg-B|STDC2|160000|1024x512|1024x512|75.25%|75.65%|-|[config](./pp_liteseg_stdc2_cityscapes_1024x512_scale0.5_160k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc2_cityscapes_1024x512_scale0.5_160k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc2_cityscapes_1024x512_scale0.5_160k/train.log)\|[vdl](https://paddlepaddle.org.cn/paddle/visualdl/service/app?id=75a52ed995914223474b3c17e628d65e)|
|PP-LiteSeg-B|STDC2|160000|1024x512|1536x768|78.75%|79.23%|-|[config](./pp_liteseg_stdc2_cityscapes_1024x512_scale0.75_160k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc2_cityscapes_1024x512_scale0.75_160k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc2_cityscapes_1024x512_scale0.75_160k/train.log)\|[vdl](https://www.paddlepaddle.org.cn/paddle/visualdl/service/app/scalar?id=a248fe1f645018306f1d4a0da33d97d6)|
|PP-LiteSeg-B|STDC2|160000|1024x512|2048x1024|79.04%|79.52%|79.85%|[config](./pp_liteseg_stdc2_cityscapes_1024x512_scale1.0_160k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc2_cityscapes_1024x512_scale1.0_160k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/cityscapes/pp_liteseg_stdc2_cityscapes_1024x512_scale1.0_160k/train.log)\|[vdl](https://www.paddlepaddle.org.cn/paddle/visualdl/service/app/scalar?id=12fa0144ca6a1541186afd2c53d31bcb)|

Note that:
* The batch size is 16 and the number of used gpu is 4 in training.
* The flip denotes flip_horizontal, the ms denotes multi scale, i.e (0.75, 1.0, 1.25) * test_resolution.
* Simliar to other models in PaddleSeg, the mIoU in above table refer to the evaluation of PP-LiteSeg on Cityscapes validation set.


**The comparisons with state-of-the-art real-time methods on Cityscapes as follows.**

|Model|Encoder|Resolution|mIoU(Val)|mIoU(Test)|FPS|
|-|-|-|-|-|-|
ENet          | -           |  512x1024   | -    | 58.3 | 76.9  |
ICNet         | PSPNet50    |  1024x2048  | -    | 69.5 | 30.3  |
ESPNet        | ESPNet      |  512x1024   | -    | 60.3 | 112.9 |
ESPNetV2      | ESPNetV2    |  512x1024   | 66.4 | 66.2 | -     |
SwiftNet      | ResNet18    |  1024x2048  | 75.4 | 75.5 | 39.9  |
BiSeNetV1     | Xception39  |  768x1536   | 69.0 | 68.4 | 105.8 |
BiSeNetV1-L   | ResNet18    |  768x1536   | 74.8 | 74.7 | 65.5  |
BiSeNetV2     | -           |  512x1024   | 73.4 | 72.6 | 156   |
BiSeNetV2-L   | -           |  512x1024   | 75.8 | 75.3 | 47.3  |
FasterSeg     | -           |  1024x2048  | 73.1 | 71.5 | 163.9 |
SFNet         | DF1         |  1024x2048  | -    | 74.5 | 121   |
STDC1-Seg50  | STDC1       |  512x1024   | 72.2 | 71.9 | 250.4 |
STDC2-Seg50  | STDC2       |  512x1024   | 74.2 | 73.4 | 188.6 |
STDC1-Seg75  | STDC1       |  768x1536   | 74.5 | 75.3 | 126.7 |
STDC2-Seg75  | STDC2       |  768x1536   | 77.0 | 76.8 | 97.0 |
PP-LiteSeg-T1 | STDC1      |  512x1024  | 73.1 | 72.0 | 273.6  |
PP-LiteSeg-B1 | STDC2      |  512x1024  | 75.3 | 73.9 | 195.3 |
PP-LiteSeg-T2 | STDC1      |  768x1536  | 76.0 | 74.9 | 143.6 |
PP-LiteSeg-B2 | STDC2      |  768x1536  | 78.2 | 77.5 | 102.6|

### CamVid

| Model | Backbone | Training Iters | Train Resolution | Test Resolution | mIoU | mIoU (flip) | mIoU (ms+flip) | Links |
|-|-|-|-|-|-|-|-|-|
|PP-LiteSeg-T|STDC1|10000|960x720|960x720|73.30%|73.89%|73.66%|[config](./pp_liteseg_stdc1_camvid_960x720_10k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/camvid/pp_liteseg_stdc1_camvid_960x720_10k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/camvid/pp_liteseg_stdc1_camvid_960x720_10k/train.log)\|[vdl](https://paddlepaddle.org.cn/paddle/visualdl/service/app?id=5685c196ff76493cecf867564c7e49be)|
|PP-LiteSeg-B|STDC2|10000|960x720|960x720|75.10%|75.85%|75.48%|[config](./pp_liteseg_stdc2_camvid_960x720_10k.yml)\|[model](https://paddleseg.bj.bcebos.com/dygraph/camvid/pp_liteseg_stdc2_camvid_960x720_10k/model.pdparams)\|[log](https://paddleseg.bj.bcebos.com/dygraph/camvid/pp_liteseg_stdc2_camvid_960x720_10k/train.log)\|[vdl](https://www.paddlepaddle.org.cn/paddle/visualdl/service/app/scalar?id=cf5223dd121d58ceff7fd93135efb573)|

Note that:
* The flip denotes flip_horizontal, the ms denotes multi scale, i.e (0.75, 1.0, 1.25) * test_resolution.
* The mIoU in above table refer to the evaluation of PP-LiteSeg on CamVid test set.