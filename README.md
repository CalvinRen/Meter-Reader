# Meter Reader

> 23Spring 重庆大学计算机学院 深度学习课程项目-任务9

<div align=center>
    <img src="./imgs/cover.jpeg" style="zoom: 30%; " />
</div>

## 项目简介
在电力能源厂区需要定期监测表计读数，以保证设备正常运行及厂区安全。但厂区分布分散，人工巡检耗时长，无法实时监测表计，且部分工作环境危险导致人工巡检无法触达。针对上述问题，希望通过摄像头拍照->智能读数的方式高效地完成此任务。

## 项目结构
```
├── README.md
├── scripts # 运行脚本
├── train_seg.py # 训练分割模型
├── train_detect.py # 训练检测模型
├── reader.py # 读数
├── data/
    ├── meter_det/ # 表计检测数据集
    ├── meter_seg/ # 指针和刻度分割数据集
├── results/ # 模型输出
├── checkpoints/ # 预训练模型
```

## 项目运行
### 1. 目标检测训练
```bash
python train_detect.py
```

### 2. 分割训练
```bash
python train_seg.py
```

### 3. 读数
```bash
python reader.py --det_model_dir output/ppyolov2_r50vd_dcn/best_model \
                 --seg_model_dir output/deeplabv3p_r50vd/best_model/ \
                 --image_dir meter_det/test/
```

## 检测 PP-YOLOv2


## 分割 DeepLabv3+


## 读数 


## 实验结果及参数
### 目标检测
| 模型 | mAP | 参数 |
| :---: | :---: | :---: |
| PP-YOLOv2 | 0.911 | [下载](https://paddledet.bj.bcebos.com/models/ppyolov2_r50vd_dcn.tar) |

### 分割
| 模型 | mIoU | 参数 |
| :---: | :---: | :---: |
| DeepLabv3+ | 0.911 | [下载](https://paddlesseg.bj.bcebos.com/models/deeplabv3p_r50vd.tar) |

### 部分结果


## 参考文献
- [1] [DeepLabv3+](https://arxiv.org/abs/1802.02611)
- [2] [PP-YOLOv2](https://arxiv.org/abs/2104.10419)
