# Final Model

Tensorflow Keras model with transfer learning layer [MobileNet-V2](https://www.kaggle.com/models/google/mobilenet-v2/frameworks/tensorFlow2/variations/130-224-classification/versions/1?tfhub-redirect=true)

## Model Summary

Model: "MobileNet-V2_nearest_600"
| Layer (type) | Output Shape | Param # |
|------------------------|--------------|-----------|
| keras_layer_1 (KerasLayer) | (None, 1001) | 5,432,713 |
| dense_1 (Dense) | (None, 2) | 2,004 |

Total params: 5434717 (20.73 MB)
Trainable params: 2004 (7.83 KB)
Non-trainable params: 5432713 (20.72 MB)

## Performance Metrics

| Metric                                 | Value  |
| -------------------------------------- | ------ |
| Accuracy                               | 1.0    |
| Precision for 'malicious'              | 1.0    |
| Recall for 'malicious'                 | 1.0    |
| F1 Score for 'malicious'               | 1.0    |
| Wall Time latency (for validation set) | 1.33 s |
