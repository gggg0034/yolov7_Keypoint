# yolov7-pose
Implementation of "YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors"

Pose estimation implimentation is based on [YOLO-Pose](https://arxiv.org/abs/2204.06806). 

在yoloV7-pose基础上添加了任意关键点数量 + 多类别分类代码。

## Training

[yolov7-w6-person.pt](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-w6-person.pt)

百度网盘：[yolov7-w6-person.pt](https://pan.baidu.com/s/12HOci-SMAQatxj3v2_sTnA)  提取码: 9nlk

``` shell
python -m torch.distributed.launch --nproc_per_node 8 --master_port 9527 train_Ncla_nPoint.py --data data/coco_kpts.yaml --cfg cfg/yolov7-w6-pose.yaml --weights weights/yolov7-w6-person.pt --batch-size 128 --img 640 --kpt-label --sync-bn --device 0,1,2,3,4,5,6,7 --name yolov7-w6-pose --hyp data/hyp.pose.yaml
```

## Deploy
TensorRT:[https://github.com/nanmi/yolov7-pose](https://github.com/nanmi/yolov7-pose)




