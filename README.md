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
```
Metadata Format

The CSV file should include the following columns:

Column Name	Description
item_id	Unique saree identifier
image_main	Path to main saree image
image_detail	Path to close-up/detail image
primary_color	Dominant saree color
secondary_color	Supporting colors
style	Style descriptors
transparency	Transparency level
occasion	Suitable occasions
mood	Mood or aesthetic impression

Example:

item_id	primary_color	secondary_color	style	occasion	mood
saree_001	white	red	elegant, soft, traditional	festive, traditional, casual	calm
saree_005	black	green, gold, silver	bold, rich, modern	party, festive, evening	bold, rich, glamorous

Required Libraries

Install the required Python libraries using:

pip install pandas matplotlib pillow opencv-python numpy ipywidgets
How to Run
Clone or download this repository.
Place the dataset folder in the correct project directory.
Open the project in Jupyter Notebook or JupyterLab.
Run the cells sequentially from top to bottom.
Use the GUI widgets to select:
Occasion
Mood
Preferred color
Top-K recommendation number
Click the Recommend Sarees button to generate recommendations.
Important Path Note

In the uploaded code, the CSV path is written as an absolute local path:

csv_path = r"C:\Users\Acer\OneDrive - University of Oklahoma\PhD in OU\Semester\Spring 2026\Computer Vision\Homeworks\Project\Datasets\sarees1.csv"

For GitHub sharing, it is recommended to replace it with a relative path:

csv_path = "Datasets/sarees1.csv"

This makes the code portable across different computers.

Computer Vision Feature Extraction

The system extracts image features using OpenCV.

Brightness

Each image is converted to grayscale, and brightness is calculated as the average grayscale intensity:

Brightness = mean(grayscale pixel values)

Grayscale values range from 0 to 255. Lower values indicate darker sarees, while higher values indicate brighter sarees.

Texture

Texture is estimated using the standard deviation of grayscale pixel values:

Texture = standard deviation(grayscale pixel values)

Higher texture values indicate greater visual complexity, such as dense motifs, intricate patterns, or detailed borders.

Recommendation Scoring

The final recommendation score combines:

CV score from brightness and texture
Metadata score from semantic attribute matching

The final score is:

Final Score = 0.75 × CV Score + 0.25 × Metadata Score

This weighting makes the system primarily image-driven while still using metadata as contextual support.

Metadata Score

The metadata score is calculated using weighted matching:

Metadata Score = 1.5 × Occasion Match
               + 1.0 × Mood Match
               + 1.0 × Primary Color Match
               + 0.5 × Secondary Color Match
               + 0.5 × Style Match

Occasion receives the highest metadata weight because event context is important for saree recommendation.

GUI

The project uses ipywidgets to create a lightweight graphical interface inside Jupyter Notebook. The GUI includes:

Dropdown menu for occasion
Dropdown menu for mood
Text box for preferred color
Slider for Top-K value
Button to generate recommendations

This allows users to interact with the system without modifying the code manually.

Evaluation

The project includes two evaluation methods.

1. Top-K Accuracy

Top-K accuracy measures whether the expected saree appears within the top K recommendations.

Top-K Accuracy = Number of Successful Test Cases / Total Test Cases × 100

In this implementation, Top-3 accuracy was used.

2. User Preference Rating

Recommendations were manually rated using a 1–5 scale:

1 = poor match
5 = excellent match

The average user preference rating was calculated to assess subjective recommendation quality.

Project Limitations
The dataset is small and prototype-scale.
Mood interpretation is based on heuristic scoring rules rather than trained machine learning models.
The current implementation focuses only on Jamdani sarees.
Blouse, petticoat, and jewelry recommendation modules are planned as future extensions.
Future Work

Future improvements may include:

Expanding the dataset with more saree types
Adding blouse, petticoat, and jewelry recommendation modules
Collecting user feedback from multiple participants
Using learned image representations or deep learning models
Applying advanced metrics such as Precision@K, Recall@K, and Mean Reciprocal Rank
Author

Lutfun Nahar Asha
PhD Student
Department of Electrical and Computer Engineering
The University of Oklahoma
