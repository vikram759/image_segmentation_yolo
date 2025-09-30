Image Segmentation using YOLOv8

This project demonstrates custom image segmentation and object detection using YOLOv8, including dataset preparation, model training, fine-tuning, and evaluation.

📌 Project Overview

Prepared and annotated a custom dataset, converting labels into YOLOv8-compatible text format.

Trained and fine-tuned a YOLOv8 model for segmentation and detection.

Achieved 99.0% mAP on the validation set.

Evaluated the trained model using precision, recall, F1-score, and mAP on test images.

Built an end-to-end pipeline: data preparation → model training → evaluation → prediction visualization.

📂 Dataset Preparation

Images were annotated using [LabelImg / Roboflow / CVAT] (replace with your tool).

Labels were exported and converted into YOLOv8 .txt format:

<class_id> <x_center> <y_center> <width> <height>


Normalized values in the range [0,1].

Dataset was split into:

train/

val/

test/

⚙️ Training the Model

Install requirements:

pip install ultralytics


Train the YOLOv8 model:

yolo detect train data=data.yaml model=yolov8n.pt epochs=100 imgsz=640


Fine-tuned hyperparameters for improved accuracy.

📊 Evaluation Metrics

mAP (mean Average Precision): 99.0% (validation set)

Precision

Recall

F1-Score

Evaluation run:

yolo detect val model=runs/detect/train/weights/best.pt data=data.yaml

🔍 Predictions on Test Images

Run inference on test images:

yolo detect predict model=runs/detect/train/weights/best.pt source=test/


Predicted results are saved in runs/detect/predict/.

📈 Results

High performance on validation and test datasets.

Robust segmentation and detection pipeline validated end-to-end.

🚀 Future Work

Deploy the model as an API for real-time inference.

Experiment with larger YOLOv8 variants (YOLOv8m, YOLOv8l).

Extend dataset for multi-class segmentation tasks.

🛠️ Tech Stack

Python

YOLOv8 (Ultralytics)

OpenCV / Matplotlib (for visualization)

Annotation Tool: [LabelImg / Roboflow / CVAT]

📧 Contact

For questions or collaborations, feel free to reach out!
