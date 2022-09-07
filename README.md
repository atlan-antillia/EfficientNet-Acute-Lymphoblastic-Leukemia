<h2>EfficientNet-Acute-Lymphoblastic-Leukemia (Updated: 2022/09/01)</h2>
<a href="#1">1 EfficientNetV2 Acute-Lymphoblastic-Leukemia Classification </a><br>
<a href="#1.1">1.1 Clone repository</a><br>
<a href="#1.2">1.2 Prepare Malaria Cell Images dataset</a><br>
<a href="#1.3">1.3 Install Python packages</a><br>
<a href="#2">2 Python classes for Malaria Cell Images Classification</a><br>
<a href="#3">3 Pretrained model</a><br>
<a href="#4">4 Train</a><br>
<a href="#4.1">4.1 Train script</a><br>
<a href="#4.2">4.2 Training result</a><br>
<a href="#5">5 Inference</a><br>
<a href="#5.1">5.1 Inference script</a><br>
<a href="#5.2">5.2 Sample test images</a><br>
<a href="#5.3">5.3 Inference result</a><br>
<a href="#6">6 Evaluation</a><br>
<a href="#6.1">6.1 Evaluation script</a><br>
<a href="#6.2">6.2 Evaluation result</a><br>

<h2>
<a id="1">1 EfficientNetV2 Acute-Lymphoblastic-Leukemia Classification</a>
</h2>

 This is an experimental Acute-Lymphoblastic-Leukemia Classification project based on <b>efficientnetv2</b> in <a href="https://github.com/google/automl">Brain AutoML</a>.
<br>
 The original Acute-Lymphoblastic-Leukemia dataset has been taken from the following web site:<br>
<a href="https://www.kaggle.com/datasets/mehradaria/leukemia">
Acute Lymphoblastic Leukemia (ALL) image dataset
</a>
<b>Data Citation:</b><br>
<pre>
Mehrad Aria, Mustafa Ghaderzadeh, Davood Bashash, Hassan Abolghasemi, Farkhondeh Asadi, 
and Azamossadat Hosseini, “Acute Lymphoblastic Leukemia (ALL) image dataset.” Kaggle, (2021). 
DOI: 10.34740/KAGGLE/DSV/2175623.
</pre>
<b>Publication Citation:</b><br>
<pre>
Ghaderzadeh M, Aria M, Hosseini A, Asadi F, Bashash D, Abolghasemi H. 
"A Fast and Efficient CNN Model for B-ALL Diagnosis and its Subtypes Classification 
using Peripheral Blood Smear Images" XXX 2021;23(4):e27468 URL: https://www.---.org DOI: - PMID: -
</pre>
<br>
<br>We use python 3.8 and tensorflow 2.8.0 environment on Windows 11.<br>
<h3>
<a id="1.1">1.1 Clone repository</a>
</h3>
 Please run the following command in your working directory:<br>
<pre>
git clone https://github.com/EfficientNet-Acute-Lymphoblastic-Leukemia.git
</pre>
You will have the following directory tree:<br>
<pre>
.
├─asset
└─projects
    └─Acute-Lymphoblastic-Leukemia
        ├─eval
        ├─evaluation
        ├─inference        
        └─test
</pre>
<h3>
<a id="1.2">1.2 Acute-Lymphoblastic-Leukemia dataset</a>
</h3>

Please download the dataset <b>Acute-Lymphoblastic-Leukemia</b> from the following web site:
<br>
<a href="https://www.kaggle.com/datasets/mehradaria/leukemia">Acute Lymphoblastic Leukemia (ALL) image dataset</a>
<br>
<br>

<pre>
.
├─asset
├─efficientnetv2-b0
└─projects
    └─Acute-Lymphoblastic-Leukemia
        ├─Acute-Lymphoblastic-Leukemia
        │  ├─test
        │  │  ├─Benign
        │  │  ├─Early
        │  │  ├─Pre
        │  │  └─Pro
        │  └─train
        │      ├─Benign
        │      ├─Early
        │      ├─Pre
        │      └─Pro
        ├─eval
        ├─evaluation
        ├─inference
        ├─models
        │  └─chief
        └─test
　...
</pre>
You can easily split the original Acute-Lymphoblastic-Leukemia dataset into train and test by running
<a href="./projects/Acute-Lymphoblastic-Leukemia/split_master.py">split_master.py</a>:
<pre>
>python split_master.py
</pre>

<br>
The number of images in train and test dataset:<br>
<img src="./projects/Acute-Lymphoblastic-Leukemia/_Acute-Lymphoblastic-Leukemia_.png" width="640" height="auto">
<br>
<br>
Sample images of Acute-Lymphoblastic-Leukemia/train/Benign:<br>
<img src="./asset/ALL_train_Benign.png" width="840" height="auto">
<br> 
<br>
Sample images of Acute-Lymphoblastic-Leukemia/train/Early:<br>
<img src="./asset/ALL_train_Early.png" width="840" height="auto">
<br> 
<br>
Sample images of Acute-Lymphoblastic-Leukemia/train/Pre:<br>
<img src="./asset/ALL_train_Pre.png" width="840" height="auto">
<br> 
<br>
Sample images of Acute-Lymphoblastic-Leukemia/train/Pro:<br>
<img src="./asset/ALL_train_Pro.png" width="840" height="auto">
<br> 
<br>


<h3>
<a id="#1.3">1.3 Install Python packages</a>
</h3>
Please run the following commnad to install Python packages for this project.<br>
<pre>
pip install -r requirements.txt
</pre>
<br>

<h2>
<a id="2">2 Python classes for Acute-Lymphoblastic-Leukemia Classification</a>
</h2>
We have defined the following python classes to implement our Acute-Lymphoblastic-Leukemia Classification.<br>
<li>
<a href="./ClassificationReportWriter.py">ClassificationReportWriter</a>
</li>
<li>
<a href="./ConfusionMatrix.py">ConfusionMatrix</a>
</li>
<li>
<a href="./CustomDataset.py">CustomDataset</a>
</li>
<li>
<a href="./EpochChangeCallback.py">EpochChangeCallback</a>
</li>
<li>
<a href="./EfficientNetV2Evaluator.py">EfficientNetV2Evaluator</a>
</li>
<li>
<a href="./EfficientNetV2Inferencer.py">EfficientNetV2Inferencer</a>
</li>
<li>
<a href="./EfficientNetV2ModelTrainer.py">EfficientNetV2ModelTrainer</a>
</li>
<li>
<a href="./FineTuningModel.py">FineTuningModel</a>
</li>

<li>
<a href="./TestDataset.py">TestDataset</a>
</li>

<h2>
<a id="3">3 Pretrained model</a>
</h2>
 We have used pretrained <b>efficientnetv2-b0</b> to train Acute-Lymphoblastic-Leukemia Model.
Please download the pretrained checkpoint file 
from <a href="https://storage.googleapis.com/cloud-tpu-checkpoints/efficientnet/v2/efficientnetv2-b0.tgz">efficientnetv2-b0.tgz</a>, expand it, and place the model under our top repository.

<pre>
.
├─asset
├─efficientnetv2-b0
└─projects
        ├─Acute-Lymphoblastic-Leukemia
  ...
</pre>

<h2>
<a id="4">4 Train</a>

</h2>
<h3>
<a id="4.1">4.1 Train script</a>
</h3>
Please run the following bat file to train our Acute-Lymphoblastic-Leukemia efficientnetv2 model by using
<b>Malaria_Cell_Images/train</b>.
<pre>
./1_train.bat
</pre>
<pre>
rem 1_train.bat
python ../../EfficientNetV2ModelTrainer.py ^
  --model_dir=./models ^
  --eval_dir=./eval ^
  --model_name=efficientnetv2-b0 ^
  --data_generator_config=./data_generator.config ^
  --ckpt_dir=../../efficientnetv2-b0/model ^
  --optimizer=rmsprop ^
  --image_size=224 ^
  --eval_image_size=224 ^
  --data_dir=./Acute-Lymphoblastic-Leukemia/train ^
  --data_augmentation=True ^
  --fine_tuning=True ^
  --monitor=val_loss ^
  --learning_rate=0.0001 ^
  --trainable_layers_ratio=0.4 ^
  --dropout_rate=0.5 ^
  --num_epochs=100 ^
  --batch_size=8 ^
  --patience=10 ^
  --debug=True  
</pre>
, where data_generator.config is the following:<br>
<pre>
; data_generation.config

[training]
validation_split   = 0.2
featurewise_center = False
samplewise_center  = False
featurewise_std_normalization=False
samplewise_std_normalization =False
zca_whitening                =False
rotation_range     = 20
horizontal_flip    = True
vertical_flip      = True
width_shift_range  = 0.1
height_shift_range = 0.1
shear_range        = 0.01
zoom_range         = [0.2, 2.0]
data_format        = "channels_last"
</pre>

<h3>
<a id="4.2">4.2 Training result</a>
</h3>

This will generate a <b>best_model.h5</b> in the models folder specified by --model_dir parameter.<br>
Furthermore, it will generate a <a href="./projects/Acute-Lymphoblastic-Leukemia/eval/train_accuracies.csv">train_accuracies</a>
and <a href="./projects/Acute-Lymphoblastic-Leukemia/eval/train_losses.csv">train_losses</a> files
<br>
Training console output:<br>
<img src="./asset/ALL_train_at_epoch_71_0831.png" width="740" height="auto"><br>
<br>
Train_accuracies:<br>
<img src="./projects/Acute-Lymphoblastic-Leukemia/eval/train_accuracies.png" width="640" height="auto"><br>

<br>
Train_losses:<br>
<img src="./projects/Acute-Lymphoblastic-Leukemia/eval/train_losses.png" width="640" height="auto"><br>

<br>
<h2>
<a id="5">5 Inference</a>
</h2>
<h3>
<a id="5.1">5.1 Inference script</a>
</h3>
Please run the following bat file to infer the skin cancer lesions in test images by the model generated by the above train command.<br>
<pre>
./2_inference.bat
</pre>
<pre>
rem 2_inference.bat
python ../../EfficientNetV2Inferencer.py ^
  --model_name=efficientnetv2-b0  ^
  --model_dir=./models ^
  --fine_tuning=True ^
  --trainable_layers_ratio=0.4 ^
  --dropout_rate=0.5 ^
  --image_path=./test/*.jpg ^
  --eval_image_size=224 ^
  --label_map=./label_map.txt ^
  --mixed_precision=True ^
  --infer_dir=./inference ^
  --debug=False 
</pre>
<br>
label_map.txt:
<pre>
Benign
Early
Pre
Pro
</pre>
<br>
<h3>
<a id="5.2">5.2 Sample test images</a>
</h3>

Sample test images generated by <a href="./projects/Acute-Lymphoblastic-Leukemia/create_test_dataset.py">create_test_dataset.py</a> 
from <a href="./projects/Acute-Lymphoblastic-Leukemia/Acute-Lymphoblastic-Leukemia/test">Acute-Lymphoblastic-Leukemia/test</a>.
<br>
<img src="./asset/ALL_test.png" width="840" height="auto"><br>


<br>
<h3>
<a id="5.3">5.3 Inference result</a>
</h3>
This inference command will generate <a href="./projects/Acute-Lymphoblastic-Leukemia/inference/inference.csv">inference result file</a>.
<br>At this time, you can see the inference accuracy for the test dataset by our trained model is very low.
More experiments will be needed to improve accuracy.<br>

<br>
Inference console output:<br>
<img src="./asset/ALL_infer_at_epoch_71_0831.png" width="740" height="auto"><br>
<br>

Inference result (inference.csv):<br>
<img src="./asset/ALL_inference_at_epoch_71_0831.png" width="740" height="auto"><br>
<br>
<h2>
<a id="6">6 Evaluation</a>
</h2>
<h3>
<a id="6.1">6.1 Evaluation script</a>
</h3>
Please run the following bat file to evaluate <a href="./projects/Acute-Lymphoblastic-Leukemia/Acute-Lymphoblastic-Leukemia/test">
Malaris_Cell_Images/test</a> by the trained model.<br>
<pre>
./3_evaluate.bat
</pre>
<pre>
rem 3_evaluate.bat
python ../../EfficientNetV2Evaluator.py ^
  --model_name=efficientnetv2-b0  ^
  --model_dir=./models ^
  --data_dir=./Acute-Lymphoblastic-Leukemia/test ^
  --evaluation_dir=./evaluation ^
  --fine_tuning=True ^
  --trainable_layers_ratio=0.4 ^
  --dropout_rate=0.5 ^
  --eval_image_size=224 ^
  --mixed_precision=True ^
  --debug=False 
</pre>
<br>

<h3>
<a id="6.2">6.2 Evaluation result</a>
</h3>

This evaluation command will generate <a href="./projects/Acute-Lymphoblastic-Leukemia/evaluation/classification_report.csv">a classification report</a>
 and <a href="./projects/Acute-Lymphoblastic-Leukemia/evaluation/confusion_matrix.png">a confusion_matrix</a>.
<br>
<br>
Evaluation console output:<br>
<img src="./asset/ALL_evaluate_at_epoch_71_0831.png" width="740" height="auto"><br>
<br>

<br>
Classification report:<br>
<img src="./asset/ALL_classification_report_at_epoch_71_0831.png" width="740" height="auto"><br>
<br>
Confusion matrix:<br>
<img src="./projects/Acute-Lymphoblastic-Leukemia/evaluation/confusion_matrix.png" width="740" height="auto"><br>

