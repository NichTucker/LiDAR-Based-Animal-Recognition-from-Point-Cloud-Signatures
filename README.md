# LiDAR-Based Animal Recognition from Point-Cloud Signatures

This repository contains the code and dataset for an Honours research project at the University of Cape Town (2025).  
The project investigates whether animals can be recognised from their point cloud signatures using LiDAR data.

---

## Overview
The pipeline processes Livox Avia LiDAR frames through:
- **Clustering and Tracking:** detect and follow moving objects across frames.  
- **Classification:** identify objects (e.g., dog, human, atlas) from cropped point-cloud regions.  
- **Temporal Fusion:** combine predictions over short sequences for improved stability.

Recordings were collected at a public dog park, providing dynamic and challenging conditions.

---

## Dataset Structure

Each numbered folder represents a single recording session (a short LiDAR sequence):

```text
Finished Dog Dataset/
│
├── manifest.json            # Global dataset index used to locate sequences
│
├── 001/                     # Sequence folder (example)
│   ├── index.jsonl           # Frame list and metadata (timestamps, alignment, etc.)
│   ├── labels/               # JSON annotations per frame
│   │   ├── 000001.json
│   │   ├── 000002.json
│   │   └── ...
│   └── points/               # LiDAR frames in binary format
│       ├── 000001.bin
│       ├── 000002.bin
│       └── ...
│
├── 002/
│   └── ...
└── ...

---


---

##  File Details

| File / Folder | Description |
|----------------|-------------|
| `manifest.json` | Lists all sequences and their relative paths. Used by the training scripts to locate files. |
| `index.jsonl` | Metadata for each frame (timestamps, calibration, etc.). |
| `labels/*.json` | Per-frame annotations with bounding boxes, class names, and track IDs. |
| `points/*.bin` | Raw Livox Avia point-cloud frames stored as float32 `[x, y, z, intensity]`. |

---

## License
MIT License © 2025 Nicholas Tucker

---

## Citation

If you use this dataset or code in your research, please cite:

> Tucker, N. (2025). *LiDAR-Based Animal Recognition from Point-Cloud Signatures.*  
> Honours Thesis, Department of Electrical Engineering, University of Cape Town.  
> [https://github.com/NichTucker/LiDAR-Based-Animal-Recognition-from-Point-Cloud-Signatures](https://github.com/NichTucker/LiDAR-Based-Animal-Recognition-from-Point-Cloud-Signatures)

