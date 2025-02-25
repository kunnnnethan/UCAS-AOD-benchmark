# UCAS-AOD-benchmark

## Introduction

This repositary rearrages files from UCAS-AOD dataset so that it can be loaded and trained in [R-YOLOv4](https://github.com/kunnnnethan/R-YOLOv4).

## Dataset repare

1. Download  UCAS-AOD [dataset](https://hyper.ai/datasets/5419).
2. Unzip dataset package into your root_dir, and rename the folder to `UCAS_AOD`.
3. Move the`ImageSets` folder which contains `train.txt`, `val.txt`,and `test.txt` into `UCAS_AOD` folder.
4. Run `data_prepare.py`, and you will obtain directory as follow:
```
root_dir
├───data_prepare.py
└───UCAS_AOD
    ├───AllImages
    │   │   P0001.png
    │   │   P0002.png
    │   │	...
    │   └───P1510.png
    ├───Annotations
    │   │   P0001.txt
    │   │   P0002.txt
    │   │	...
    │   └───P1510.txt       
    ├───ImageSets 
    │   │   train.txt
    │   │   val.txt
    │   └───test.txt  
    ├───test
    │   └───...
    ├───train
    │   └───...
    ├───val
    │   └───...
    ├───CAR
    ├───PLANE
    └───Neg
```

**notes**: The integrated dataset contains 1510 images, with train set 755, val set 302, test set 452(following DOTA division 5:2:3). Files are numbered from 1-1510, in which `1-510` are cars, `511-1510` are airplanes. Besides, classname is attached to label file in format of  `classname x1 y1 x2 y2 x3 y3 x4 y4 theta lx ly w h ` ,

for example:

```
car  2.763971e+02	9.125021e+01	2.911375e+02	3.823406e+01	3.308891e+02	4.928647e+01	3.161486e+02	1.023026e+02	1.055379e+02	2.787673e+02	3.876027e+01	4.975157e+01	6.301615e+01	
car  3.002141e+02	1.003123e+02	3.209637e+02	4.665470e+01	3.566901e+02	6.047021e+01	3.359405e+02	1.141279e+02	1.111416e+02	3.055889e+02	4.856245e+01	4.572642e+01	6.365764e+01	
...
```

