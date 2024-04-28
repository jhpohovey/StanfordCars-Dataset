# StanfordCars

The Stanford Cars dataset was proposed by Krause et. al in *3D Object Representations for Fine-Grained Categorization*. The citation is at the bottom of this document. 

It seems that most online resources, e.g., [1](https://github.com/sigopt/stanford-car-classification), [2](https://github.com/cyizhuo/Stanford-Cars-dataset), [3](https://github.com/nguyentruonglau/stanford-cars), [4](https://github.com/kimx3314/Stanford-Cars-Dataset-Vehicle-Recognition/tree/master) are either broken or incomplete. Downloading from the [kaggle](https://www.kaggle.com/datasets/jessicali9530/stanford-cars-dataset) is one approach, but this doesn't include test set annotation. 

Originally, this dataset could be loaded from the torchvision library using the following line:
```
dataset = torchvision.datasets.StanfordCars(".", download=True)
```

But per the [docs](https://pytorch.org/vision/main/generated/torchvision.datasets.StanfordCars.html) and [`pytorch/vision#7545`](https://github.com/pytorch/vision/issues/7545), the hosting site has been broken for some time.

So, the data can be cloned from here instead:

The structure of the dataset follows the above linked issue:
```
└── stanford_cars
    └── cars_test_annos_withlabels.mat
    └── cars_train
        └── *.jpg
    └── cars_test
        └── .*jpg
    └── devkit
        ├── cars_meta.mat
        ├── cars_test_annos.mat
        ├── cars_train_annos.mat
        ├── eval_train.m
        ├── README.txt
        └── train_perfect_preds.txt
```

```
@INPROCEEDINGS{6755945,
  author={Krause, Jonathan and Stark, Michael and Deng, Jia and Fei-Fei, Li},
  booktitle={2013 IEEE International Conference on Computer Vision Workshops}, 
  title={3D Object Representations for Fine-Grained Categorization}, 
  year={2013},
  volume={},
  number={},
  pages={554-561},
  abstract={While 3D object representations are being revived in the context of multi-view object class detection and scene understanding, they have not yet attained wide-spread use in fine-grained categorization. State-of-the-art approaches achieve remarkable performance when training data is plentiful, but they are typically tied to flat, 2D representations that model objects as a collection of unconnected views, limiting their ability to generalize across viewpoints. In this paper, we therefore lift two state-of-the-art 2D object representations to 3D, on the level of both local feature appearance and location. In extensive experiments on existing and newly proposed datasets, we show our 3D object representations outperform their state-of-the-art 2D counterparts for fine-grained categorization and demonstrate their efficacy for estimating 3D geometry from images via ultra-wide baseline matching and 3D reconstruction.},
  keywords={Three-dimensional displays;Geometry;Solid modeling;Design automation;Training data;Training;Feature extraction},
  doi={10.1109/ICCVW.2013.77},
  ISSN={},
  month={Dec},}
```

