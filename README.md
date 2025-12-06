# Fruit Object Detection — YOLOv5

> Object detection pipeline for fruit images. Reproducible training, inference, and evaluation with YOLOv5.

---

## 1) Goals / Main Objective
- Train a lightweight, high-precision object detector to recognize and localize fruits (apple, banana, orange) in images.
- Produce a reproducible pipeline (data → labels → train → evaluate → infer) that a reviewer or hiring manager can run end-to-end.
- Deliver clear model performance metrics, representative qualitative results (predicted bounding boxes), and actionable insights for deployment or further research.

---

## 2) Problem Definition
Detect and classify fruit objects in images. This is a multiclass object detection task where each object instance is annotated with a bounding box and a class label in YOLO format. The desired outcome is a high mean Average Precision (mAP) at common IoU thresholds and robust generalization to unseen images.

**Applications:** inventory automation, quality control in agriculture, retail self-checkout, mobile visual search, and academic demonstration of applied computer vision.

## 3) Dataset & Directory Structure
Expected YOLO-style layout:

```
/dataset
  /images
    /train
    /val
  /labels
    /train
    /val
```

## 4) Frameworks & Libraries Used
- **Framework:** YOLOv5 (Ultralytics)
- **Language:** Python 3.x
- **Major libraries:** PyTorch, OpenCV, NumPy, pandas, matplotlib, scikit-learn (for metrics), xml/ET (for annotation conversion)
- **Environment:** Google Colab (recommended) or any CUDA-enabled Linux machine with NVIDIA GPU

## 6) Project Highlights
- End-to-end reproducible pipeline: annotation conversion → training → evaluation → inference.
- Lightweight base model (`yolov5s`) used for fast iteration and proof-of-concept.
- Notebook includes utility functions for visual validation of labels and predictions.
- Clear instructions for exporting to ONNX/TensorRT for deployment.

---

## 7) Model Performance

### Quantitative summary 
| Metric       | Value     |
|--------------|----------:|
| mAP@0.5      | **0.906** |
| Precision    | **0.876** |
| Recall       | **0.819** |
| F1-score     | **0.846** |
| Best epoch   | **48** |


Provide a per-class AP table here (fill with your numbers):

| Class   | Images | Instances | Precision (P) | Recall (R) | mAP@0.5 | mAP@0.5–0.95 |
|--------:|-------:|----------:|--------------:|-----------:|--------:|-------------:|
| **all** | 59     | 112       | 0.876         | 0.819      | 0.906   | 0.649        |
| apple   | 59     | 30        | 0.862         | 0.900      | 0.937   | 0.752        |
| banana  | 59     | 40        | 0.879         | 0.675      | 0.831   | 0.455        |
| orange  | 59     | 42        | 0.889         | 0.881      | 0.952   | 0.741        |

```markdown
![example detection 1](docs/figures/example1.jpg)
![example detection 2](docs/figures/example2.jpg)
![example detection 3](docs/figures/example3.jpg)
```