# Edge AI GStreamer Apps
> Repository to host GStreamer based Edge AI applications for TI devices

This Github Repository adds support for **Face Mask Detection** Using [EDGE-AI-STUDIO](https://www.ti.com/tool/EDGE-AI-STUDIO) Model Composer  for TI Embedded Processor.

## 1. Face Mask Detection
Face Mask detection is the task of detecting whether or not a person is wearing a mask. 
This Project will catagories a person in one of the three catagories.
1. With Correct Mask
2. With Incorrect Mask
3. No Mask

This Project uses Object detection in Edge AI Studio to Classify the Person in one of the three Categories and make Bounding boxes around their faces.

## 2. Understanding and Connecting Devices
A Link of Detailed Documentation of the Devices are given below:
1. TDA4VM : (https://software-dl.ti.com/jacinto7/esd/processor-sdk-linux-edgeai/TDA4VM/08_06_00/exports/docs/common/sdk_overview.html)
2. AM62A  : (https://software-dl.ti.com/jacinto7/esd/processor-sdk-linux-edgeai/AM62AX/08_06_00/exports/docs/common/sdk_overview.html)
3. AM68A  : (https://software-dl.ti.com/jacinto7/esd/processor-sdk-linux-edgeai/AM68A/08_06_00/exports/docs/common/sdk_overview.html)

The above documents tells in details how to start the board, and run the sample apps on that.

## 3. Edge AI Studio Model Composer
The [Edge AI studio model composer](https://dev.ti.com/modelcomposer/) train , optimize and Compile the AI model for TI Embedded Processor. 
Currently, the Edge AI Studio can compose Object detection and Image Classification Task.

**Supported Devices for Edge AI Studio Model Composer**

| **DEVICE**              | **Supported**      |
| :---:                   | :---:              |
| AM62A                   | :heavy_check_mark: |
| AM68A                   | :heavy_check_mark: |
| SK-TDA4VM               | :heavy_check_mark: |

## 4. Steps to Use Edge AI Studio Model Composer
Below are the steps to use Edge AI Studio Model Composer


### 4.1 EdgeAI Studio setup
1. On the model Composer main page, On the top bar of the GUI, click on Options → Serial Port Settings.
2. If TI Cloud Agent is not installed on your system, a prompt will appear with instructions on how to do so.
3. Install the TI cloud Agent.
4. ADD [TICloudAgent Bridge](https://chrome.google.com/webstore/detail/ticloudagent-bridge/pfillhniocmjcapelhjcianojmoidjdk) extension to the browser.
5. RELOAD the page, and reopen the Serial Port Settings.
6. Model Composer should automatically detect the appropriate serial port and baud rate to use. The Port and Baud Rate settings can be changed. However, it is recommended to use the default detected values.
:o: Note: If using a Windows computer, the user may need to install additional drivers for ports to show up. (https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers).\
Click on the link. Go to Downloads. Download and install ***CP210x Windows Drivers with Serial Enumerator***.
- For more details , on the main page go to "help --> Quick Start Guide" or  [click here](https://software-dl.ti.com/ccs/esd/training/workshop/edgeaistudio/modelcomposer_quick_start_guide.html)

### 4.2. Creating the project
1. Click on create new project.
2. From task type Drop Down menu select "Object detection" or "Image Classification" based on the task.
3. Write name of project
4. Click Start Composing

### 4.3. Dataset Preparation
Data can taken from various input sources. Click on the Input Source.
1. **PC Camera:** The Images can directly be taken using Inbuilt PC camera. Click on the PC Camera and select a Camera from the available Camera list, Select the image format from "JPG" and "PNG".
2. **Device Camera:**
3. **Import Images from Local PC:** Existing datasets can be imported directly in JPG, PNG format. Click onImport Images from Local PC. Select a folder from the local PC. On the right panel select the images and click Confirm.  
4. **Import Annotated Archive dataset:** Annotated archive data can also be imported.

:o: *Note that the data annotated outside the edgeAI Studio can not be imported. Only the data which are annotated and Downloaded from edge AI studio, that can be uploaded.*

### 4.4. Data Annotations
Once dataset is imported, data annotation can be done.

**Steps for annotating For Object Detection:**
1. Select a image from the left panel.
2. Click on the Square like shape left to the image.
3. Drag on the image where Box is to be drawn.
4. Fill / Select the label in pop up.
5. Repeat for All the images.
Note: Image can be zoomed , dragged aside also. Try all the icons left to the image.

**Steps for annotating For Object Detection:**
1. In classification first add all the label.
2. Click on the '+' icon on the top right.
3.  In the Pop Up window, Click on the + icon on the bottom left.
4.  Enter the label name and hit enter.
5.  Now select image from the left panel and select the label from right panel.
6.  Repeat for all the images.

Once Done with the annotations, the annotated data can be downloaded by clicking on Download symbol above the left panel.
It is recommended to Download the Annotated Data, incase by mistake project got deleted.


### 4.5. Model Selection
Once all the data is annotated, move to the next section.\
**Device Selection:** Select the Target device. Drag the slider to find the best trade-off between power and performance for your task.\
**Model Selection:**  Select a model according to the need "faster accuracy" or "faster Performance"

### 4.6. Train
Tune the training Parameter According to need. And Click on the start training button on the top-right.
The training Performance will be Shown as shown in below image.

![plot](images/training_log.png)

Once the model is trained go to the next Section Compilation.


### 4.7. Compilation
In Compilation Section, Choose the compilation parameters from the drop down.
If accuracy is not priority and only you need to compile to see the result select the "Best Speed Preset". 
After that Hit Start Compiling.
It will take some good amount of time.

After Compilation is over, the screen will be something like below image.

![plot](images/compiled_model.png)

Click on **Download the Artifact to PC** to Download the Compiled model on the Local PC.

:o: Note: Download the model to your PC before closing the browser. It will not be available when you log in again if you do not download it first.

The Downloaded model will look like this:

![plot](images/Model_directory.png)

### 4.8. Live Preview

Once the model is compiled , Live Preview can be done. In live preview we can test our compiled model with live camera.
Some setting needs to be done before live preview.
Follow these step to live preview:
1. Select Live preview in the top part of the page.
2. Connect the board to PC by UART cable.
3. At the bottom left click on capsule like icon. After clicking , Hardware connected will be shown at bottom left.

![Connect to ti agent](images/TI_agent.png)

4. Press the Device Setup button to configure the development board.
5. Press the Start Live preview button to download the model from the server to the EVM and run the preview.

## 5. Deployment on Board
Model can be Deployed on the board in two ways:
1. Connect the board and click Deploy model on board.
2. Manually Copying the Model on the board.

### 5.1 Connecting Board to PC using UART
1. Install the [MobaXterm](https://mobaxterm.mobatek.net/download.html) to the PC to remotely connect to the Board.
2. Once installed connect the board to the PC through the UART cable. 
3. Open MobaXterm and Click on session.
4. Click on the Serial and select a Port from the drop down.
5. Baud rate should be configured to **115200** bps in serial port communication program. 

:o: Note: If using a Windows computer, the user may need to install additional drivers for ports to show up. (https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers).\
Click on the link. Go to Downloads. Download and install ***CP210x Windows Drivers with Serial Enumerator***.

6. Once the port are visible, Connect to all the ports and Reboot the board. 
7. The boot log will be visible in one of the ports. Other ports may be closed.
8. In login prompt : type `root` as user.
9. Your current directory in terminal will be like: `/opt/edgeai-gst-apps`

### 5.2 Connecting remotely using SSH
 You can also access the device with the IP address that is shown on the display. With the IP address one can ssh directly to the board.\
 In MObaXterm:
 1. Click session
 2. Click SSH
 3. Enter the IP displayed at board
 4. Hit enter
 5. In the login prompt:  type `root` as user.
 
One Can also use **VS code** to remotely login using SSH.

After login when You go to the `/opt` the directory structure will be like this:

![SDK Directory](images/SDK_directory.png)

`/opt/edgeai-gst-apps`  Contains the apps to run the model.\
`/opt/model_zoo` contains all the model. The downloaded model from the EDGE AI STUDIO will be saved here.\
`/opt/edgeai-test-data` contains the input data ( image , videos to run the model ).


**Copying Downloaded model to the board**

We can use `scp` Command to copy the model from our PC to the board.
1. Open your terminal
2. Go to the directory where Model is saved.
3. Type the following command:

```scp -r model_folder_name root@ip_address_of_board:/opt/model_zoo```

![copying_model](images/copying_model.png)


## 6. Testing on the board


### 6.1. Importing data on the board
Before Importing Images to the board, Rename the images file sequentially.
```0000.png , 0001.png ,0002.png ......... 000n.png```
It will help in slide showing images on the screen.

To copy the data to the board `scp` command can be used again.
1. Go to the folder where image folder is located.
2. Type the below command.
`scp -r image_folder_name root@ip_address_of_device:/opt/edgeai-test-data`
3. Hit enter
4. All the images files will be copied to `opt/edgeai-test-data/image_folder_name`

![copying_images](images/scp_for_image.png)


### 6.2. Making Configuration file
Next task is to make Configuration file for the project. 
The config folder is located at `opt/edgeai-gst-apps/configs`
(You can make a copy of the existing `.yaml` file and edit it or else you can make a new `.yaml` file.)

**Component of config file**

```
title: "Face Mask Detection"
log_level: 2
inputs:
    input0:
        source: /dev/video2
        format: jpeg
        width: 1280
        height: 720
        framerate: 30
    input1:
        source: /opt/edgeai-test-data/videos/video_0000_h264.h264
        format: h264
        width: 1280
        height: 720
        framerate: 30
        loop: True
    input2:
        source: /opt/edgeai-test-data/Mask_dataset/%04d.png
        width: 1280
        height: 720
        index: 0
        framerate: 1
        loop: True
models:
    model0:
        model_path: /opt/model_zoo/20230530-081846_yolox_s_lite_onnxrt_TDA4VM
        alpha: 0.4
    model1:
        model_path: /opt/model_zoo/ss-8720
        alpha: 0.4
    model2:
        model_path: /opt/model_zoo/ONR-SS-8610-deeplabv3lite-mobv2-ade20k32-512x512
        alpha: 0.4
outputs:
    output0:
        sink: kmssink
        width: 1920
        height: 1080
        overlay-performance: True
    output1:
        sink: /opt/edgeai-test-data/output/output_video.mkv
        width: 1920
        height: 1080
    output2:
        sink: /opt/edgeai-test-data/output/output_image_%04d.jpg
        width: 1920
        height: 1080

flows:
    flow0: [input2,model0,output0,[320,180,1280,720]]
```

1. inputs :  
This include all the input sources.\
We can have multiple input : input 0,input 1 ....... input n.\
             `source: /dev/video2` is for the camera connected to te board.\
             `source: /opt/edgeai-test-data/videos/video_0000_h264.h264` is for the video dataset saved at the given location.\
             `source: /opt/edgeai-test-data/Mask_dataset/%04d.png` is for the images at the`/opt/edgeai-test-data/Mask_dataset` . Note that the images will go one by one for input as slide show.

2. models :   
Like inputs we can have different model. Path of the model in model_zoo needs to be specified here.

3. outputs:  
In this section, output path is specified.\
`kmssink` correspond to the Monitor connected to the board.\
We can also save the results as video or images files by specifying their path.

4. flows :  
In flow we specify the combination of input source ,model name and outputs destination.  
For example:  
`flow0: [input2,model0,output0,[320,180,1280,720]]`  
This means use input 2, model 0, and output 0 to run.    
[320,180,1280,720]  
In this the first number and second number is for X and Y coordinate respectively from where we want to display the result on the monitor.  
The Third number shows the length of result to be shown along X axis .  
The Fourth number shows the length of result to be shown along Y axis .  


:o: Note that we can write many flows using different combination of input , model and output. And we can see multiple output on the monitor. 



## 7. Running the Model
Once You have done below three things:
1. Copied model to the board
2. Copied dataset to the Board
3. Added Config file

The Model is ready to run.
We can run the model using python-apps or CPP apps.
To run the Model with python apps:
1. Go to `/opt/edgeai-gst-apps/apps_python`
2. Type `./app_edgeai.py ../configs/config_file_name.yaml` in Terminal and hit Enter.

![copying_images](images/run.png)



## 8. Post Processing

In Object Detection , We will get a bounding Box with label around the Object.\
Apart from this we can Add some Custom Post Processing. And show some meaning full result.\
In this Face Mask Detection Project, Following Post Processing Has been used:
1. Total Number of Detected faces
2. Different color of the bounding boxes for the different label
3. Count of each label

```
 # Calculating the bounding boxes of each type
        b_num=0 # total number of bounding boxes
        num_correct=0
        num_incorrect=0
        num_nomask=0
        for b in bbox:
            if b[5] > self.model.viz_threshold:
              b_num=b_num+1
              if int(b[4])==2:
                num_correct=num_correct+1
              if int(b[4])==1:
                num_nomask=num_nomask+1
              if int(b[4])==0:
                num_incorrect=num_incorrect+1
```

- In the above Code, b[5] is the probability of correct prediction. So if the probability is greater than a particular threshold (`self.model.viz_threshold`) then only bounding box will be created.
- b[4] corresponds to the class id.

**The code changes done to add post-processing logic for can be found in this** [commit](https://github.com/saurabh260120/edgeai-gst-apps-face-mask-detection/commit/9a6d30fc3e86e56d235f63f11907682cd05af262).  


## Result

![Result1](images/output_image_0004.jpg)

![Result2](images/output_image_0009.jpg)

<br/>
<p align="center">
<img src="images/face_mask.gif" width="640" title="Resultant Output">
</p> 
