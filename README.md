# Improved YOLOv8 algorithm

Here we make some improvements in YOLOv8-obb algorithm. 

![1-net-new](C:\Users\MSI-NB\Downloads\1-net-new.PNG)

 We add Mixed local channel attention and the dynamic upsampling module for higher detection accuracy and Generalized ELAN module for a lightweight architecture.

![image-20241107213948962](C:\Users\MSI-NB\AppData\Roaming\Typora\typora-user-images\image-20241107213948962.png)

# Requirements

- CUDA 10.0
- PyTorch 2.2
- Python 3.10



# Getting Started

We recommend to use colab for a quick start in our project. Here is our default training commend. 

```python
from ultralytics import YOLO
model=YOLO('/content/ultralytics/cfg/models/v8/yolov8-obb.yaml')
#model = YOLO("yolov8n-obb.pt")
model.train(data="/content/ultralytics/cfg/datasets/dota8.yaml", epochs=150,imgsz=800)  # 训练模型
```

Here is our default evaluating commend.

```python
from ultralytics import YOLO
model=YOLO('/content/ultralytics/cfg/models/v8/yolov8-obb.yaml')
model = YOLO("/content/best.pt")
model.val(data="/content/ultralytics/cfg/datasets/dota8.yaml",imgsz=800,batch=4)
```



# Dataset

In this project we mainly use DOTAv1 dataset, which is a wide-spread open-source dataset. 



# Citation

Please cite this paper if you want to use it in your work.

