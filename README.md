# mAP (mean Average Precision)

This code will evaluate the performance of your neural net for object recognition.

## Explanation
First (**1.**), we calculate the Average Precision (AP), for each of the classes present in the ground-truth. Finally (**2.**), we calculate the mAP (mean Average Precision) value.

## Prerequisites

You need to install:
	python3,
	matplotlib [optional],
	opencv-python [optional]
	
## Running the code

Step by step:

  1. Create folder "input", within which create "ground-truth" and "detection-results"
  2. [Create the ground-truth files](#create-the-ground-truth-files)
  3. Copy the ground-truth files into the folder **input/ground-truth/**
  4. [Create the detection-results files](#create-the-detection-results-files)
  5. Copy the detection-results files into the folder **input/detection-results/**
  6. Run the code:
         ```
         python main.py
         ```
  7. Input the minimum overlap threshold (e.g. 0.5 or 0.75 or 0.95)
         
#### Create the ground-truth files

- Create a separate ground-truth text file for each image.
- Use **matching names** for the files (e.g. image: "image_1.jpg", ground-truth: "image_1.txt").
- In these files, each line should be in the following format:
    ```
    <class_name> <left> <top> <right> <bottom> [<difficult>]
    ```
- The `difficult` parameter is optional, use it if you want the calculation to ignore a specific detection.
- E.g. "image_1.txt":
    ```
    tvmonitor 2 10 173 238
    book 439 157 556 241
    book 437 246 518 351 difficult
    pottedplant 272 190 316 259
    ```

#### Create the detection-results files

- Create a separate detection-results text file for each image.
- Use **matching names** for the files (e.g. image: "image_1.jpg", detection-results: "image_1.txt").
- In these files, each line should be in the following format:
    ```
    <class_name> <confidence> <left> <top> <right> <bottom>
    ```
- E.g. "image_1.txt":
    ```
    tvmonitor 0.471781 0 13 174 244
    cup 0.414941 274 226 301 265
    book 0.460851 429 219 528 247
    chair 0.292345 0 199 88 436
    book 0.269833 433 260 506 336
    ```
    
    Graphs are stored in **/results** folder
