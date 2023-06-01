# Edge AI GStreamer Apps
> Repository to host GStreamer based Edge AI applications for TI devices

This Github Repository adds support for **Face Mask Detection** Using [EDGE-AI-STUDIO](https://www.ti.com/tool/EDGE-AI-STUDIO) Model Composer  for TI Embedded Processor.

## Face Mask Detection
Face Mask detection is the task of detecting whether or not a person is wearing a mask. 
This Project will catogorise a person in one of the three catogories.
1. With Correct Mask
2. With Incorrect Mask
3. No Mask

This Project usese Objcet detection in Edge AI Studio to Classify the Person in one of the three Categories and make Bounding boxex around their faces.

## Understanding and Connecting Devives
A Link of Detailed Documentation of the Devices are given below:
1. TDA4VM : (https://software-dl.ti.com/jacinto7/esd/processor-sdk-linux-edgeai/TDA4VM/08_06_00/exports/docs/common/sdk_overview.html)
2. AM62A  : ( )
3. AM68A  :

The above documents tells in details how to start the board, and run the sample apps on that.

## Edge AI Studio Model Composer
The [Edge AI studio model composer](https://dev.ti.com/modelcomposer/) train , optimize and Compile the AI model for TI Embedded Processor. 
Currently, the Edge AI Studio can compose Object detection and Image Classification Task.

### Supported Devices for Edge AI Studio Model Composer

| **DEVICE**              | **Supported**      |
| :---:                   | :---:              |
| AM62A                   | :heavy_check_mark: |
| AM68A                   | :heavy_check_mark: |
| SK-TDA4VM               | :heavy_check_mark: |

## Steps to Use Edge AI Studio Model Composer
Below are the steps to use Edge AI Studio Model Composer

### 1. Creating the project
1. Click on create new project.
2. From task type Drop Down menu select "Object detection" or "Image Classification" based on the task.
3. Write name of project
4. Click Start Composing

### 2. Dataset Preparation
Data can taken from various input sources. Click on the Input Source.
1. **PC Camera:** The Images can directly be taken using Inbuilt PC camera. Click on the PC Camera and select a Camera from the available Camera list, Select the image format from "JPG" and "PNG".
2. **Device Camera:**
3. **Import Images from Local PC:** Existing datasets can be imported directly in JPG, PNG format. Click onImport Images from Local PC. Select a folder from the local PC. On the right panel select the images and click Confirm.  
4. **Import Annotated Archive dataset:** Annotated archive data can also be imported.
\:warning: *Note That the data annotated outside the edgeAI Studio can not be imported. Only the data which are annotated and Downloaded from edge AI studio, that can be uploaded.*

### 2. Data Annotations
Once dataset is imported, data annotation can be done.

**Steps for annotating For Object Detection:**
1. Select a image from the left panel.
2. Click on the Square like shape left to the image.
3. Drag on the image where Box is to be drawn.
4. Fill / Select the lable in pop up.
5. Repeat for All the images.
Note: Image can be zoomed , dragged aside also. Try all the icons left to the image.

**Steps for annotating For Object Detection:**
1. In classification first add all the label.
2. Click on the '+' icon on the top right.
3.  In the Pop Up window, Click on the + icon on the bottom left.
4.  Enter the lable name and hit enter.
5.  Now select image from the left panel and select the lable from right panel.
6.  Repeat for all the images.

Once Done with the annotations, the annotated data can be downloaded by clicking on Download symbol above the left panel.
It is recommended to Download the Annotated Data, incase by mistake project got deleted.


### 3. Model Selection
Once all the data is annotated, move to the next section.
**Device Selection:** Select the Target device. Drag the slider to find the best trade-off between power and performance for your task.
**Model Selection:**  Select a model acording to the need "faster accuracy" or "faster Perfomance"

### 4. Train
Tune the training Parameter Acording to need. And Click start training on the top-right.
The trainig Perfomance will be Shown.


### 5. Compilation


### 5. Live Preview


### 6. Deployment on Board



