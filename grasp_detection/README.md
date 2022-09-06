# grasp_detection




### Main system requirements:
- CUDA 11.1.1
- Python 3.8
- TensorFlow v2.4.1



### Quick Start
1. Clone this repository
```
git clone https://github.com/ivalab/grasp_multiObject_multiGrasp.git
cd grasp_multiObject_multiGrasp
```

2. Build Cython modules
```
cd lib
make clean
make
cd ..
```

3. Install [Python COCO API](https://github.com/cocodataset/cocoapi)
```
cd data
git clone https://github.com/pdollar/coco.git
cd coco/PythonAPI
make
cd ../../..
```

4. Put models under `output/res50/train/default/`
4. Run demo

```
./tools/demo_graspRGD.py --net res50 --dataset grasp
```
6. Run with own images

If you want to run demo with your own images,  just put your image into `./data/demo/` and change file path in `./tools/demo_graspRGD.py`



### Train

1. Generate data
   1-1. Download [Cornell Dataset](http://pr.cs.cornell.edu/grasping/rect_data/data.php)
   1-2. Run `dataPreprocessingTest_fasterrcnn_split.m` (please modify paths according to your structure)
2. Train

```
./experiments/scripts/train_faster_rcnn.sh 0 graspRGB res50
```





### Thanks

[GitHub - ivalab/grasp_multiObject_multiGrasp: An implementation of our RA-L work 'Real-world Multi-object, Multi-grasp Detection'](https://github.com/ivalab/grasp_multiObject_multiGrasp)
