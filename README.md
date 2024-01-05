# YOLOv8-GUI-Monitoring-Code
This project utilizes YOLOv8 Object Detection for GUI monitoring, applicable to overseeing multiple remote machine screens displaying numerical values and statuses. Leveraging pre-labeled classes such as Information panels, Battery levels, and machine states (Run or Error) as shown in example images, the project simulates a GUI using **Visual Basic .NET** and generates a dataset.

The recognition action for the Information panel requires new data to be added every five seconds; otherwise, a warning is triggered. The recognition process for the Battery level involves utilizing **Tesseract-OCR** for optical character recognition (OCR) to extract the current battery level. If the detected level falls below a predefined threshold, a warning will be triggered.

Warning actions utilize [Line Notify](https://notify-bot.line.me/zh_TW/) to send alert messages to user accounts or groups, with reminders sent after a specified time interval.

Additionally, considering not all computers are equipped with GPUs, this project introduces **OpenVINO** to enable accelerated predictions on systems without a GPU but with an Intel CPU.

## YOLOv8
[Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) is a cutting-edge, state-of-the-art (SOTA) model that builds upon the success of previous YOLO versions and introduces new features and improvements to further boost performance and flexibility. YOLOv8 is designed to be fast, accurate, and easy to use, making it an excellent choice for a wide range of object detection and tracking, instance segmentation, image classification and pose estimation tasks.

## Tesseract-OCR
[Tesseract-OCR](https://github.com/UB-Mannheim/tesseract) is an open-source optical character recognition (OCR) engine developed by Google. It is designed to recognize printed text, supports multiple languages, and finds widespread applications in the field of text recognition. Tesseract-OCR provides a robust text recognition capability, enabling the conversion of text from images into machine-readable textual data for programmable processing.

## OpenVINO
[OpenVINO](https://www.intel.com/content/www/us/en/developer/tools/openvino-toolkit/overview.html), short for Open Visual Inference and Neural network Optimization, is an open-source toolkit developed by Intel. It is designed to optimize and accelerate visual inference workloads, supporting various hardware architectures, including Intel CPUs, GPUs, VPUs, and more. OpenVINO provides a unified solution, enabling developers to easily deploy deep learning models on different hardware platforms while delivering efficient inference performance.

## Steps to run Code
### Create Virtual Environment
* After creating the virtual environment, install the required packages.(The Python version is 3.8)

        pip install torch==1.13.1+cu116 torchvision==0.14.1+cu116 torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu116
        pip install ultralytics pytesseract openvino-dev[pytorch]==2023.0.2
* Clone the repository
  
        git clone https://github.com/KennyChen880127/YOLOv8-GUI-Monitoring-Code.git
* Goto cloned folder
  
        cd YOLOv8-GUI-Monitoring-Code
### Predicting
You can use the GUI dataset that I have already trained with YOLOv8n for predictions, or you can use the models provided by YOLOv8, see [Detection Docs](https://docs.ultralytics.com/tasks/detect/) for usage examples with these models.

* [yolov8n_monitor.pt](https://drive.google.com/file/d/1fyWY9jxjvpERyZ9sS8UnWBhUnfQotqXA/view?usp=drive_link)

* Use the following command to predict

        python detect.py
  
### Results
| Situation One | Situation Two |
| ------------- | ------------- |
|  |  |
