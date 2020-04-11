# Automated Cell Detection

```
python train.py --epochs 110 --data training/tissues.data --cfg training/yolov3.cfg --batch 1 --accum 1 --weights ''

python  -c "from models import *; convert('training/yolov3.cfg', 'weights/best.pt')"

python detect.py --source data/samples/black_bubbles_1.jpg --weights converted.weights --cfg training/yolov3.cfg --names training/classes.names
```