###### &#x20;**Object Detection with YOLOv5 and YOLOv8**



**Table of Contents**

\- \[Sample Images]

\- \[Project Overview]

\- \[What I Did]

\- \[Requirements]

\- \[Usage]

\- \[Results]

\- \[Lessons Learned]

\- \[Author]



**Sample Images**

!\[Office Workspace](images/live.png)

!\[Clutter Dataset](images/detect.png)

!\[Clutter Dataset](images/img.png)



!\[Office Workspace Test](images/live.png) :--

\*This is a detection result on a photo of our office workspace, used to test the custom clutter dataset.\*





**Project Overview**

This project explores \*\*object detection\*\* using the YOLO (You Only Look Once) models.  

I started with \*\*YOLOv5\*\* for detection and training on a custom clutter dataset and some images from a known dataset. Later, I experimented with \*\*YOLOv8\*\* to see if performance could be improved. YOLOv8 required more careful tuning, which taught me the importance of dataset quality and parameter optimization.







**What I Did**

\- Installed PyTorch, OpenCV, and YOLO dependencies.

\- Ran YOLOv5 detection on webcam and sample images.

\- Uploaded and prepared a \*\*custom clutter dataset\*\* (plus some images from an existing dataset).

\- Trained YOLOv5 with custom parameters (`--img 640 --batch 16 --epochs 50`).

\- Switched to YOLOv8 for optimization/tuning to test performance improvements.

\- Visualized detection results and training progress.



\---



**Requirements**

\- Python 3.10+  

\- Jupyter Notebook / Google Colab  

\- Libraries: `torch`, `torchvision`, `torchaudio`, `opencv-python`, `ultralytics`  



Install dependencies:

```bash

pip install torch torch vision torchaudio --index-url https://download.pytorch.org/whl/cpu

pip install opencv-python

pip install ultralytics





**USAGE**

**YOLO v5**

\--Clone the repo and install requirements:

git clone https://github.com/ultralytics/yolov5

cd yolov5

pip install -r requirements.txt



\--Run detection:

python detect.py --source data/images/bus.jpg --weights yolov5s.pt --conf 0.4



\--Train on custom dataset:

python train.py --img 640 --batch 16 --epochs 50 --data data.yaml --weights yolov5s.pt --name clutter\_detector



**YOLOv8**

\--Install ultralytics:

pip install ultralytics



\--Run detection:

from ultralytics import YOLO

model = YOLO("yolov8n.pt")

results = model("bus.jpg")



\--Train:

model.train(data="data.yaml", epochs=50, imgsz=640)





**Results**

* YOLOv5 gave stable detection results on sample images and the clutter dataset.



* YOLOv8 was tested for optimization, but initial outputs were poor — showing the need to rework dataset preparation and training parameters.



* Detection outputs are saved in runs/detect/.



* Training results (loss curves, metrics) are saved in runs/train/.



**Lessons Learned**

* Dataset preparation is critical — directory structure and data.yaml must be correct.



* YOLOv5 is easier to set up and stable for beginners.



* YOLOv8 offers better performance potential but requires careful tuning.



* Experimenting with both versions helped me understand trade-offs between stability and optimization.



**Author**

Chukwuemeka Chimamanda — Student \& aspiring AI/ML engineer

&#x20; 

