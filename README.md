# inference_benchmark

Notes:
1. provided two frozen graphs files for effcientnet-b0, one with (1,224, 224, 3) as input shape one with no shape
2. input name: input_tensor; output name: softmax_tensor
3. python inference.py --model efficientnet-b0.pb --data_dir /path_to_imagenet_val_tfrecord --batch_size 1 --intra 1 --inter 16
4. added efficientnet-S.pb which is from efficientnet-edgetpu-S, please modify the inference.py to do the test.
Change MEAN_RGB and STDDEV_RGB to [127.0,127.0,127.0] and [128.0,128.0,128.0], and notice this model has 1001 classes instead of 1000

2080TI, 
TensorFlow (FP32)

efficientnet-b0
    top1 accuracy: 76.62
    top5 accuracy: 93.03
    latency_mean(ms): 7.6744
	
efficientnet-S.pb:
    top1 accuracy: 77.31
    top5 accuracy: 93.66
    latency_mean(ms): 4.4133


TensorRT
FP32

efficientnet-b0
    top1 accuracy: 76.62
    top5 accuracy: 93.03
    latency_mean(ms): 3.4078
	
effcientnet-edgetpu-S
    top1 accuracy: 77.31
    top5 accuracy: 93.66
    latency_mean(ms): 2.2195

FP16

efficientnet-b0
    top1 accuracy: 76.63
    top5 accuracy: 93.03
    latency_mean(ms): 3.2828
	
effcientnet-edgetpu-S
    top1 accuracy: 77.32
    top5 accuracy: 93.66
    latency_mean(ms): 1.5076

INT8

Renset50-INT8
	top5 accuracy: 93.11
	latency_mean(ms): 1.4580
