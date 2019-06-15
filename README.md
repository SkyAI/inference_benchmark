# inference_benchmark

Notes:
1. provided two frozen graphs files for effcientnet-b0, one with (1,224, 224, 3) as input shape one with no shape
2. input name: input_tensor; output name: softmax_tensor
3. python inference.py --model efficientnet-b0.pb --data_dir /path_to_imagenet_val_tfrecord --batch_size 1 --intra 1 --inter 16


