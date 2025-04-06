📁 Dataset
Source: Satellite images of Burdur Lake
Images and corresponding masks are loaded using tf.keras.utils.image_dataset_from_directory.
Images are resized to 256x256 and converted to grayscale for model input.

🔄 Data Preprocessing
Masks and images are separated based on class labels.
Converted RGB to grayscale using TensorFlow's tf.image.rgb_to_grayscale.
Normalized values to range [0, 1].
Split into training and test sets using train_test_split.

🧠 Model Architecture: U-Net
The model follows the classic U-Net architecture with:
Encoder blocks: 4 downsampling steps with convolution, activation (ELU), and max-pooling.
Bottleneck: 2 convolutional layers.
Decoder blocks: 4 upsampling steps with skip connections.
Final output: Sigmoid activation for binary segmentation.

⚙️ Training
Optimizer: Adam
Loss: BinaryCrossentropy
Metrics: Accuracy
EarlyStopping is used to prevent overfitting.

📊 Evaluation
Performance is evaluated using:
Accuracy
Jaccard Score
Classification Report
Model prediction vs. ground truth masks are visualized.
Training and validation loss/accuracy curves are plotted.

🧪 Results
Trained model is saved as model1.h5.

Visualization shows clear improvement in segmenting water regions.

Jaccard Score and classification report indicate good performance on the test set.

