```{=html}
<div align="center">
```
`<br>`{=html}
```{=html}
<p>
```
Face Detection is one of the most common and yet most complex deep
learning problem. This model is made via a pipeline of Yolov5 and SSD
using FaceNet (in Keras). Yolov5 is used for Face Detection in an image,
video or live feed and the detected face is cropped and then tested via
SSD to check whether it exists in the provided database.
```{=html}
</p>
```
\#\#

::: {align="center"}
Yolov5 Base Code
:::

This model is built upon a Yolov5 model that can be trained for a custom
network. This model was paired wtih pre trained weight for Face
detection in an image which was further optimized for the faces we
required to work on. The original [Yolov5
repo](https://github.com/ultralytics/yolov5) can be used if any other
network is to be built.

\#\#

::: {align="center"}
Quick Start
:::

::: {align="left"}
```{=html}
<details open>
```
`<summary>`{=html}Install`</summary>`{=html}

Copy the required code in a directory. The requirements.txt file
contains all the required packages in a
[**Python\>=3.7.0**](https://www.python.org/) environment, including
[**PyTorch\>=1.7**](https://pytorch.org/get-started/locally/).

In most case you'll be directly running the API, so no need to run the
requirements.txt file.
```{=html}
</details>
```
```{=html}
<details open>
```
`<summary>`{=html}Run API`</summary>`{=html}

The best approach would be to create a conda enviornemnt and run the
following command to automatically check the requirements and run the
API.

``` {.bash}
cd files
python run.py
```

`<summary>`{=html}Use API`</summary>`{=html}

The API provided 4 options: 1. Run inference on Custom Image 2. Run
inference on WebCam 3. Run inference on all files in directory
resources/test\_images 4. Register a new face (Is cropped to face
automatically) and set its class to add a new entity.

```{=html}
</details>
```
```{=html}
<details open>
```
`<summary>`{=html}Run detect.py`</summary>`{=html}

In case you directly want to use the console instead of the API, you can
run the following commands. **NOTE: YOU WILL HAVE TO RUN
requirements.txt FIRST**

``` {.bash}
cd files
pip install -r requirements.txt  # install
```

Running detect.py directly gives you more control over the different
arguments. Also, you can use different modes to run the inference. For
WebCam:

``` {.bash}
python detect.py --weights resources/face_yolo5.pt --conf 0.25 --source 0 --model_json resources/keras-facenet-h5/model.json --model_h5 resources/keras-facenet-h5/model.h5 --ssd_images resources
```

For Video Feed (Place video in resources/test\_images and specify the
name of file in --source given below):

``` {.bash}
python detect.py --weights resources/face_yolo5.pt --conf 0.25 --source resources/test_images/file_name.MOV --model_json resources/keras-facenet-h5/model.json --model_h5 resources/keras-facenet-h5/model.h5 --ssd_images resources
```

For Test Folder:

``` {.bash}
python model_api.py --weights resources/face_yolo5.pt --conf 0.25 --source resources/test_images --model_json resources/keras-facenet-h5/model.json --model_h5 resources/keras-facenet-h5/model.h5 --ssd_images resources
```

```{=html}
</details>
```
:::
