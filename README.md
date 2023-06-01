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
The Edge AI studio model composer train , optimize and Compile the AI model for TI Embedded Processor. 
Currently, the Edge AI Studio can compose Object detection and Image Classification Task.

### Supported Devices for Edge AI Studio Model Composer

| **DEVICE**              | **Supported**      |
| :---:                   | :---:              |
| AM62A                   | :heavy_check_mark: |
| AM68A                   | :heavy_check_mark: |
| SK-TDA4VM               | :heavy_check_mark: |

## Steps to Use Edge AI Studio Model Composer
Below are the steps to use Edge AI Studio Model Composer

### 1. Preparing Dataset



