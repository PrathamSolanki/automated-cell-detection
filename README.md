# Automated Cell Detection

Made use of the PyTorch YOLOv3 software developed by Ultralytics LLC. Available [here](https://github.com/ultralytics/yolov3).

1. Manually annotated the images using [LabelImg](https://github.com/tzutalin/labelImg). Saved the annotations in YOLO style text files.

2. Restructured the project according to the guidlines available [here](https://github.com/ultralytics/yolov3/wiki/Train-Custom-Data).

3. Made use of the existing scripts as follows:

```
python train.py --epochs 110 --data training/tissues.data --cfg training/yolov3.cfg --batch 1 --accum 1 --weights ''

python  -c "from models import *; convert('training/yolov3.cfg', 'weights/best.pt')"

python detect.py --source data/samples/black_bubbles_1.jpg --weights converted.weights --cfg training/yolov3.cfg --names training/classes.names
```