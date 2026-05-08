# Change Detection and Blob Matching

Computational Vision mid-term submission.
Mojtaba Alehosseini, student number 5965588.

This repository holds my work for the motion analysis mid-term. The full
report is in the PDF; the notebook reproduces every figure end to end on
Google Colab.

## Files

* `midterm_change_detection.ipynb`: the Colab notebook, committed with
  all cells already executed. Every figure, table and printed number
  renders directly on GitHub.
* `midterm_report.pdf`: the written report covering the same material,
  with an analysis paragraph after each experiment and a conclusions
  section at the end.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Mojtaba-Alehosseini/Change-Detection-Blob-Matching/blob/main/midterm_change_detection.ipynb)

## What it does

The pipeline follows the motion analysis lectures. I build a background
image from the first few frames (optionally with a running average
update), threshold the absolute difference against the current frame,
clean the binary map with morphological operations, label connected
components, and match those blobs across frames. Two threshold rules are
compared (a noise amplitude heuristic and Otsu) and two matching
strategies (centroid distance and a combined distance plus area ratio
similarity). An optional persistent tracker integrates matches across
longer time spans by holding a stable ID across short detection gaps.

## Data

The provided station frames and the three videos I recorded live in a
shared Drive folder, since they are too heavy to commit here:

<https://drive.google.com/drive/folders/1FjfZQHf1bOG1xqY3cY-6ulMtjcgD_3UX?usp=sharing>

Inside the folder:

* `station_video_frames/es1/video/` is the provided station sequence.
* `station_video_frames/5965588/test1.mp4` is the moving camera video (44 MB).
* `station_video_frames/5965588/test2.mp4` is the steady camera video (22 MB).
* `station_video_frames/5965588/test3.mp4` is a shorter, lower resolution clip of the same scene as test2 (1 MB).

## Reproducing the run

1. Open the Drive link above.
2. Right click the `Change_detection` folder and choose
   "Add shortcut to Drive". Place it under
   `MyDrive/CV_LABS/Lab_Motion/Lab3/`.
3. Open the notebook in Colab using the badge above.
4. Run the Drive mount cell at the top, then Run All.

The notebook uses absolute Drive paths, so the shortcut is what makes it
portable to a different account. For the full analysis without running
anything, the PDF and the rendered notebook on GitHub are enough.
