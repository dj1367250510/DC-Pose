# DC-Pose
When our paper is accepted, we will publish all the code！
***
# Environment Setting
## Our Code has been tested with:
- Ubuntu 20.04
- python 3.9.0
- Cuda 11.6
- PyTorch 1.12.0
## Some dependent packages：
- [Gorilla](https://github.com/Gorilla-Lab-SCUT/gorilla-core)
```
pip install gorilla-core==0.2.5.3
```
- [PointNet2](https://github.com/erikwijmans/Pointnet2_PyTorch)
```
cd model/pointnet2
python setup.py install
```
# Data Processing
## NocsDatesets:CAMERA25 and REAL275
- Download and preprocess the dataset following [DPDN](https://github.com/JiehongLin/Self-DPDN)
- Download and unzip the segmentation results [here](http://home.ustc.edu.cn/~llinxiao/segmentation_results.zip)
- Put them under ```./data```and the final file structure is as follows:
```
data
├── camera
│   ├── train
│   ├── val
│   ├── train_list_all.txt
│   ├── train_list.txt
│   ├── val_list_all.txt
├── real
│   ├── train
│   ├── test
│   ├── train_list.txt
│   ├── train_list_all.txt
│   └── test_list_all.txt
├── segmentation_results
│   ├── CAMERA25
│   └── REAL275
├── camera_full_depths
│   ├── train
│   └── val
├── gts
│   ├── val
│   └── real_test
├── obj_models
│   ├── train
│   ├── val
│   ├── real_train
│   └── real_test
```
## IndoorDataset:HouseCat6D
HouseCat6D:A Large-Scale Multi-Modal Category Level 6D Object Perception Dataset with Household Objects in Realistic Scenarios(CVPR2024)
- Download and preprocess the dataset following [HouseCat6D](https://sites.google.com/view/housecat6d)
- Put them under ```./HouseCat6D```and the final file structure is as follows: 
```
HouseCat6D
├── scene01
│── scene02
│── scene03
...........
│── scene34
│── obj_models_small_size_final
│── val_scene1
│── val_scene2
│── test_scene1
...............
│── test_scene6
```
# Train code of command blocks
- Train On the NocsDateset:
```
python train.py --config config/REAL/camera_real.yaml
```
- Train On the IndoorDataset:
```
python train_housecat6d.py --config config/HouseCat6D/housecat6d.yaml
```
# Evalute code of command blocks
- Evaluate On the NocsDateset:
```
python test.py --config config/REAL/camera_real.yaml --test_epoch 30
```
- Evaluate On the IndoorDataset:
```
python test_housecat6d.py --config config/HouseCat6D/housecat6d.yaml --test_epoch 150
```
# Results
You can download our pre-trained models on NOCS and HouseCat6D datasets [here](https://drive.google.com/file/d/1cOebQI2dteexKNhTh5UddpU1QyJPbS9R/view?usp=drive_link), along with evaluation metrics for each category.
## The result of REAL275:
| Metrics | IoU50 | IoU75 | 5 degree 2 cm | 5 degree 5 cm | 10 degree 2 cm | 10 degree 5 cm |
|:----:|:----:|:----:|:----:|:----:|:----:|:----:|
| Ours | 84.2 | 80.7 | 60.4 | 66.6 | 78.4 | 86.5 |
## The result of CAMERA25:
| Metrics | IoU50 | IoU75 | 5 degree 2 cm | 5 degree 5 cm | 10 degree 2 cm | 10 degree 5 cm |
|:----:|:----:|:----:|:----:|:----:|:----:|:----:|
| Ours | 94.3 | 91.8 | 78.4 | 82.4 | 86.4 | 91.6 |
## The result of HouseCat6D:
| Metrics | IoU50 | IoU75 | 5 degree 2 cm | 5 degree 5 cm | 10 degree 2 cm | 10 degree 5 cm |
|:----:|:----:|:----:|:----:|:----:|:----:|:----:|
| Ours | 78.6 | 55.9 | 22.3 | 23.4 | 53.5 | 56.5 |
# 💭 Video
Please check our video for more qualitative results.
The predictions and ground truths are shown by red and green bounding boxes, respectively.
![](https://youtu.be/4qY8LFR9PH4)
# TODO 
- Upload all code
- Upload log(pre-model)
- Add video

