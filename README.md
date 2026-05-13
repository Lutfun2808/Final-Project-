# Personalized Saree Recommendation Expert System Using Computer Vision

This project implements a computer vision-based saree recommendation system designed for Bangladeshi cultural contexts. The system recommends Jamdani sarees based on user-selected occasion, mood, and preferred color. It combines OpenCV-based image feature extraction with metadata-based semantic matching to generate ranked recommendations.

## Project Overview

The goal of this project is to assist users in selecting suitable sarees by considering both visual appearance and contextual information. The system analyzes saree images using computer vision features such as brightness and texture, while also using manually assigned metadata such as color, mood, style, transparency, and occasion.

The final recommendation system is CV-dominant, meaning that image-based features contribute more strongly to the final ranking than metadata.

## Features

- Personal Jamdani saree dataset
- CSV-based metadata organization
- OpenCV-based feature extraction
- Brightness calculation from grayscale image intensity
- Texture estimation using grayscale standard deviation
- CV-dominant recommendation scoring
- Metadata-based semantic matching
- Top-K recommendation output
- Jupyter Notebook GUI using `ipywidgets`
- Top-K accuracy evaluation
- User preference rating evaluation

## Dataset Structure

The dataset should be organized as follows:

```text
Project/
│
├── My_Final_CV_Project.py
├── README.md
│
└── Datasets/
    ├── sarees1.csv
    └── sarees/
        ├── saree_001_main.jpg
        ├── saree_001_detail.jpg
        ├── saree_002_main.jpg
        ├── saree_002_detail.jpg
        ├── saree_003_main.jpg
        ├── saree_003_detail.jpg
        ├── saree_004_main.jpg
        ├── saree_004_detail.jpg
        ├── saree_005_main.jpg
        └── saree_005_detail.jpg
