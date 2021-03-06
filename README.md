
# Mask R-CNN for Object Detection and Segmentation
This is a close repository for the [Matterport MASK RCNN](https://github.com/matterport/Mask_RCNN). The config, coco, model file has been updated for the coco custom dataset. The program has been implemented in the google colab. The tensorflow-object-detection.ipynb file can get you started. Whole file contains the A to Z implementation of the mask r-cnn for the insulator object detection





This is an implementation of [Mask R-CNN](https://arxiv.org/abs/1703.06870) on Python 3, Keras, and TensorFlow. The model generates bounding boxes and segmentation masks for each instance of an object in the image. It's based on Feature Pyramid Network (FPN) and a ResNet101 backbone.









## Installation
1. Clone this repository
    ```bash
    !git clone https://github.com/atiqureee51/insulator-mask-rcnn.git
    %cd /content/insulator-mask-rcnn

    ```

2. Install dependencies
   ```bash
   !pip uninstall -y tensorflow
   !pip3 install -r requirements.txt
   !pip uninstall tensorboard-plugin-wit
   !pip install -q tensorboard==1.14.0 
   ```
3. Run setup from the repository root directory
    ```bash
    !python3 setup.py install
    !pip show insulator-mask-rcnn
    ls
    ```
   
4. add datasets directory and file
```bash
fileId = 'google drive file id here... file should be in zip file'

os.makedirs('datasets')
os.chdir('datasets')

auth.authenticate_user()
gauth = GoogleAuth()
gauth.credentials = GoogleCredentials.get_application_default()
drive = GoogleDrive(gauth)

fileName = fileId + '.zip'
downloaded = drive.CreateFile({'id': fileId})
downloaded.GetContentFile(fileName)
ds = ZipFile(fileName)
ds.extractall()
os.remove(fileName)
print('Extracted zip file ' + fileName)

%cd /content/insulator-mask-rcnn
```

4. RUN the main ipynb file google colab. It will guide you to the whole process and will produce the output.
5. The dataset has been collected from IEEE dataport in public domain [INSULATOR DEFECT DETECTION](https://ieee-dataport.org/competitions/insulator-defect-detection) And please cite them when you use. 

####
IMPORTANT TALKS:

1. To make any annotation I have [makesense.ai] (https://www.makesense.ai/) is much more useful to annotate any object easily. For coco export, annotate using polygon and export in COCO, VGG JSON, VOC XML format etc. Though they doesn't store or save anything but it is handy when you want to change your train-test. Just upload the image files there of the new train set and import annotation of whole. It will just create annotation for the train set thre and you can export it.
2.  for joining two coco files and merge together use the following [github link](https://github.com/mohamadmansourX/Merge_COCO_FILES).
3.  All releases is in [here](https://github.com/atiqureee51/insulator-mask-rcnn/releases)




## Citation
Use this bibtex to cite this repository:
```
@misc{matterport_maskrcnn_2017,
  title={Mask R-CNN for object detection and instance segmentation on Keras and TensorFlow},
  author={Waleed Abdulla},
  year={2017},
  publisher={Github},
  journal={GitHub repository},
  howpublished={\url{https://github.com/matterport/Mask_RCNN}},
}
```
