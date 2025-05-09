# YOLOvBub
This repository acts as an appendix for my Bachelor Thesis, YOLOvBub. It contains various materials that could not be included in the written document itself, such as links to sources, video examples of detections, and the Jupyter Notebooks containing the code that was used.

<details>
<summary>Abstract</summary>

As time goes by, the subsea technology industry continuously expands its operations, which necessitates additional funds, resources, and research into new technology. However, such growth often also brings negative aspects with it, with one concrete example being noise pollution. For each issue, there is at least one type of solution that is proposed and implemented, and in the case of underwater noise pollution, an efficient and low-cost proposition is the use of a bubble curtain. However, bubble curtains do not have inbuilt monitoring systems, despite the importance of keeping these systems running at maximum efficiency. Therefore, a gap in existing research unfolds. 

We introduce YOLOvBub, a YOLOv10-based deep learning model specialized in detecting underwater bubble activity. Two additional accompaniments to our system include BubSET and BubSET-Testing, two datasets that facilitate the training and validation process, respectively. 

Our approach yields reasonable results. The best performing model from our experiments reaches a mean average precision of 0.891 at an IoU threshold of 0.5, along with a precision value of 0.84 and a recall value of 0.88. The model also demonstrates a solid understanding of the provided material, with a large majority of the detections observed in the test footage having a confidence value of 0.9 and higher.

By fine-tuning the YOLOv10-M model for our specific task, shifting the model's focus more towards correct classification as opposed to bounding box placement and implementing a wide range of image augmentations, we create an original proposal for the issue, with the hopes of fostering further research into underwater object detection and computer vision as a whole.

</details>

# Repository Structure

- **Metrics/**  
    Detailed validation metrics and result summaries for the models tested.

- **Notebooks/**  
    Jupyter Notebooks used for data preparation, model training, evaluation, and result visualization.

- **Videos/**  
    Video examples showcasing the YOLOvBub detection system in action.

- **Weights/**
    Includes `.pt` files for the base models validated during our studies.

- **PDF/**
    Includes a `.pdf` to the Bachelor Thesis document.

- **dataset-links.txt**  
    Links to the BubSET and BubSET-Testing datasets used in training and validation, hosted on Roboflow.

- **sources.txt**  
    List of external references and video sources.

# Performance Metrics

The following table summarizes the validation metrics for each model configuration tested during the YOLOvBub experiments.

| Config                | Total Time | Origin     | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 | Fitness |
|-----------------------|------------|------------|-----------|--------|---------|--------------|---------|
| 14042025             | 6.1 hours  | Pretrained | 0.727     | 0.710  | 0.733   | 0.461        | 0.488   |
| 14042025-20finetune  | 23 min     | 14042025   | 0.824     | 0.854  | 0.864   | 0.607        | 0.632   |
| 14042025-40finetune  | 46 min     | 14042025   | 0.853     | 0.848  | 0.874   | 0.617        | 0.642   |
| 15042025             | 3.3 hours  | Pretrained | 0.855     | 0.832  | 0.880   | 0.619        | 0.645   |
| 15042025-20finetune  | 23 min     | 15042025   | 0.857     | 0.858  | 0.889   | 0.623        | 0.650   |
| 15042025-40finetune  | 46 min     | 15042025   | 0.863     | 0.838  | 0.886   | 0.608        | 0.630   |
| 16042025             | 1.3 hours  | Pretrained | 0.895     | 0.847  | 0.898   | 0.621        | 0.648   |
| 16042025-20finetune  | 23 min     | 16042025   | 0.833     | 0.874  | 0.885   | 0.624        | 0.650   |
| 16042025-40finetune  | 46 min     | 16042025   | 0.828     | 0.880  | 0.892   | 0.627        | 0.652   |
| 18042025             | 3.2 hours  | Pretrained | 0.840     | 0.883  | 0.891   | 0.642        | 0.666   |
| 18042025-20finetune  | 23 min     | 18042025   | 0.823     | 0.889  | 0.874   | 0.621        | 0.646   |
| 18042025-40finetune  | 46 min     | 18042025   | 0.868     | 0.860  | 0.890   | 0.624        | 0.650   |

# Acknowledgement

This model was mainly based on [YOLOv10](https://github.com/THU-MIG/yolov10) by Ultralytics. 
The dataset creation, preprocessing, and annotation processes were facilitated by [Roboflow](https://roboflow.com/).