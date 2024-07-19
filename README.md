# TC-Pose
When our paper is accepted, we will publish all the code！
***
# 💜 Environment Setting
## 💢 Our Code has been tested with:
- Ubuntu 20.04
- python 3.9.0
- Cuda 11.6
- PyTorch 1.12.0
## 🗯 Some dependent packages：
- [Gorilla](https://github.com/Gorilla-Lab-SCUT/gorilla-core)
```
pip install gorilla-core==0.2.5.3
```
- [PointNet2](https://github.com/erikwijmans/Pointnet2_PyTorch)
```
cd model/pointnet2
python setup.py install
```
# 💛 Data Processing
## NocsDateset:CAMERA25 and REAL275
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
# TODO 
- Upload all code
- Upload training code and verification code command blocks
- Add result table
- Add video

