# Carya-Data-code
The following code is used for data processing.
This toolkit includes 5 core scripts covering the entire data preparation workflow:

1. Data Augmentation & Class Balancing (augment_and_balance.py)
Function: Performs automated data augmentation with a focus on solving class imbalance.

Key Features:

Uses the Albumentations library for robust transformations (Flip, Crop, Affine, Color Jitter, Blur, Noise, etc.).

Smart Balancing: Automatically searches for an optimal copy/oversampling strategy to ensure all classes (especially rare ones) achieve a target distribution (e.g., 30%–40%) in the final training set.

Automatically merges the augmented training set with the original validation and test sets into a unified directory structure.

2. Stratified Dataset Splitting (stratified_split.py)
Function: Splits a raw dataset into Train, Validation, and Test sets (default: 6:2:2) while maintaining class distribution.

Key Features:

Rare Class Awareness: Specifically designed to handle datasets with "rare" classes. It separates data into "rare" and "common" pools before splitting to ensure the rare class is represented proportionally in every subset.

3. YOLO to VOC Converter (yolo_to_voc.py)
Function: Converts YOLO .txt labels to Pascal VOC .xml format.

Key Features:

Denormalizes YOLO coordinates (0-1) to absolute pixel coordinates.

Includes boundary clipping logic to ensure bounding boxes do not exceed image dimensions.

Generates standard XML trees compatible with tools like LabelImg.

4. YOLO to COCO Converter (yolo_to_coco.py)
Function: Converts YOLO-style segmentation labels to the standard COCO JSON format (instances.json).

Key Features:

Designed for Instance Segmentation: Handles Polygon coordinates (points) rather than just bounding boxes.

Automatically calculates polygon Area and bounding box (BBox) for the JSON output.

5. Label Analysis (labels_analyze.py)
Function: A utility to quickly count and visualize the distribution of classes in your dataset.

Key Features:

Supports both YOLO (.txt) and VOC (.xml) formats.

Outputs total object counts per class and total number of bounding boxes.
