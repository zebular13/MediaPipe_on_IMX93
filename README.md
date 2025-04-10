# MediaPipe_on_IMX93
Running the MediaPipe Models on MaaXBoard OSM93.


## Getting started

clone the [blaze_app_python](https://github.com/zebular13/blaze_app_python/tree/imx) repository here: 
```
git clone https://github.com/zebular13/blaze_app_python/tree/imx 
```
This is a python implementation of the MediaPipe framework.

Download the models: 

```
cd blaze_app_python
cd blaze_tflite_imx
cd models
./get_tflite_models.sh
```

This includes the float32 pose, hand and face models (check the script for details) as well as the quantized pose, hand and face models. 

To convert the quantized models to [vela](https://github.com/nxp-imx/ethos-u-vela), run:
```
vela [modelname.tflite]
```

**Note:** only INT8 or UINT8 quantized models can be converted to vela.  

Once the models have been downloaded, you can run inference using the script in the ```blaze_tflite_imx``` folder:
```
python3 blaze_detect_live_gstreamer.py -b face -q
```

You can refer to the [README](https://github.com/zebular13/blaze_app_python/blob/imx/blaze_tflite_imx/README.md) for more launch arguments.


## Tutorials


* To learn how to get started on the MaaXBoard OSM93, please refer to the following Getting Started Guide on Hackster:
http://avnet.me/MLonOSM93

<img src="https://github.com/user-attachments/assets/eb8b7a1f-c78f-4d42-8537-0e6f54ef508b" width="400">

* To learn how to quantize your own models (necessary for deployment on the i.MX93's ethos-U65 NPU) please refer to [Part 1: Accelerating AI on the MaaXBoard OSM93 – Quantization](http://avnet.me/acceleratingAIonOSM93-part1).

<img src="https://github.com/user-attachments/assets/b39084a6-18ee-47f5-ba1d-8cb23ee14663" width="400">

* To learn how to convert models to vela, check out [Part 2: Accelerating AI on the MaaXBoard OSM93 – Vela Conversion](http://avnet.me/acceleratingAIonOSM93-part2)

<img src="https://github.com/user-attachments/assets/22518602-14f8-4cd9-ad77-4b8113f52895" width="400">

* Finally, learn how to convert your image pipeline to NNStreamer in [Part 3: Accelerating AI on the MaaXBoard OSM93 – NNStreamer](https://www.hackster.io/monica/accelerating-ai-on-maaxboard-osm93-camera-pipeline-822c68)

<img src="https://github.com/user-attachments/assets/36d09101-051c-43ba-8ce0-01db4bc35ca7" width="400">

