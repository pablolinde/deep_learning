## Transfer-learning with MobileNetV3Small

This notebook applies transfer learning techniques using [MobileNetV3Small](https://www.tensorflow.org/api_docs/python/tf/keras/applications/MobileNetV3Small) network pre-trained on [ImageNet](https://image-net.org/download.php). The models were tested using the [rock-paper-scissors](https://storage.googleapis.com/download.tensorflow.org/data/rps.zip) dataset. 
It downloads and preprocesses the dataset, then compares three different transfer learning approaches:

- Training from scratch: using MobileNetV3 without pre-trained weights.
- Feature extraction: using MobileNetV3 with all its layers frozen, using its convolutional base as a feature extractor.
- Fine-tuning: unfreezing some layers of MobileNetV3 to allow further training.

Each method is evaluated using accuracy, confusion matrices, and training time.
