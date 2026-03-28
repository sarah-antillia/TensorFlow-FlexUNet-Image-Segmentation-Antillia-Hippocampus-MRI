<h2>TensorFlow-FlexUNet-Image-Segmentation-Antillia-Hippocampus-MRI (2026/03/28)</h2>
Sarah T. Arai<br>
Software Laboratory antillia.com<br><br>
This is the first experiment of Image Segmentation for <b>Antillia (AT) Hippocampus MRI</b> 
 based on 
our <a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet</a>
 (<b>TensorFlow Flexible UNet Image Segmentation Model for Multiclass</b>), and a 256x256 pixels PNG
 <a href="https://drive.google.com/file/d/16ZMhGpJBL0kAPARE6zVoBKPz_nnEZzUz/view?usp=sharing">
Antillia-Hippocampus-MRI-ImageMask-Dataset.zip</a> 
(<a href="https://creativecommons.org/licenses/by-sa/4.0/">
CC BY-SA 4.0
</a>), which was derived by us from <br><br>
<a href="https://www.kaggle.com/datasets/ag3ntsp1d3rx/Hippocampus">
<b>Hippocampus MRI Slices</b>
</a> on the kaggle.com
<br><br>
<hr>
<b>Actual Image Segmentation for Antllia-Hippocampus-MRI Images of 256x256 pixels</b><br>
As shown below, the inferred masks predicted by our segmentation model trained by the dataset appear similar to the 
ground truth masks.
<br><br>
<b> class_color_map = {Anterior:cyan,  Posterior:yellow }</b>
<br><br>
<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10035.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10035.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10035.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10068.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10068.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10068.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10172.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10172.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10172.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>1. Dataset Citation</h3>
The dataset used here was taken from <br><br>
<a href="https://www.kaggle.com/datasets/ag3ntsp1d3rx/Hippocampus">
<b>Hippocampus MRI Slices</b>
</a> on the kaggle.com
<br><br>
The following explanation was taken from the above kaggle web site.<br><br>
<b>About Dataset</b><br>
High-resolution MRI Hippocampus images and segmentation masks derived from the Medical Segmentation Decathlon challenge.
<br><br>
File Information:<br>
<ul>
<li>images/ – Percentile-normalized MRI slices (0–1 float32 TIFF) resized to 256×256, coronal view.</li>
<li>labels/Anterior – Binary segmentation masks for anterior Hippocampus (uint8 {0,255} TIFF).</li>
<li>labels/Posterior – Binary segmentation masks for posterior Hippocampus (uint8 {0,255} TIFF).</li>
</ul>
<br>
On the derivation of our new PNG dataset, please refer to the repository 
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI">
TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI</a>
<br><br>
<b>License</b><br>
<a href="https://creativecommons.org/licenses/by-sa/4.0/">
CC BY-SA 4.0</a>
<br>
<br>
<h3>
<a id="2">
2 Antillia-Hippocampus-MRI ImageMask Dataset
</a>
</h3>
 If you would like to train this Antillia-Hippocampus-MRI Segmentation model by yourself,
 please download the dataset from the google drive  
 <a href="https://drive.google.com/file/d/16ZMhGpJBL0kAPARE6zVoBKPz_nnEZzUz/view?usp=sharing">
Antillia-Hippocampus-MRI-ImageMask-Dataset.zip</a> (<a href="https://interoperable-europe.ec.europa.eu/licence/creative-commons-attribution-40-international-cc-40">
CC BY 4.0
</a>)
, expand the downloaded ImageMaskDataset and put it under <b>./dataset</b> folder to be:
<br>
<pre>
./dataset
└─AT-Hippocampus-MRI
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
        ├─images
        └─masks
</pre>
<br>
<b>AT-Hippocampus-MRI Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/AT-Hippocampus-MRI_Statistics.png" width="512" height="auto"><br>
<br><br>
As shown above, the number of images of train and valid datasets is large enough to use for the
 training set of our segmentation model.
<br><br>
<br>
<b>Train_images_sample</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_masks_sample</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/train_masks_sample.png" width="1024" height="auto">
<br>

<h3>
3 Train TensorFlowFlexUNet Model
</h3>
 We trained AT-Hippocampus-MRI TensorFlowFlexUNet Model by using the 
<a href="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
, which simply runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>

<b>Model parameters</b><br>
Defined a small <b>base_filters = 16 </b> and large <b>base_kernels = (11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large num_layers (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
;You may specify your own UNet class derived from our TensorFlowFlexModel
model         = "TensorFlowFlexUNet"
image_width    = 256
image_height   = 256
image_channels = 3
input_normalize = True
normalization  = False
num_classes    = 5
base_filters   = 16
base_kernels   = (11,11)
num_layers     = 8
dropout_rate   = 0.05
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_crossentropy" and <a href="./src/dice_coef_multiclass.py">"dice_coef_multiclass"</a>.<br>
<pre>
[model]
loss           = "categorical_crossentropy"
metrics        = ["dice_coef_multiclass"]
</pre>
<b>Dataset class</b><br>
Specifed <a href="./src/ImageCategorizedMaskDataset.py">ImageCategorizedMaskDataset</a> class.<br>
<pre>
[dataset]
class_name    = "ImageCategorizedMaskDataset"
</pre>
<br>
<b>Learning rate reducer callback</b><br>
Enabled learing_rate_reducer callback, and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.4
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with patience parameter.
<pre>
[train]
patience      = 10
</pre>
<b>RGB Color map</b><br>
Specifed rgb color map dict for AT-Hippocampus-MRI 1+2 classes.<br>
<pre>
[mask]
mask_datatyoe    = "categorized"
mask_file_format = ".png"
;AT-Hippocampus-MRI rgb color map dict for 1+2 classes.
rgb_map = {(0,0,0):0, (0,255,255):1,(255,255,0):2, }
</pre>
<b>Epoch change inference callback</b><br>
Enabled <a href="./src/EpochChangeInferencer.py">epoch_change_infer callback</a></b>.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
num_infer_images         = 6
</pre>
By using this callback, on every epoch_change, the inference procedure can be called
 for 6 images in <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> 
<br> 
As shown below, early in the model training, the predicted masks from our UNet segmentation model showed 
discouraging results.
 However, as training progressed through the epochs, the predictions gradually improved. 
 <br> 
<br>
<b>Epoch_change_inference output at starting (epoch 1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at middlepoint (epoch 21,22,23)</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/epoch_change_infer_at_middle.png" width="1024" height="auto"><br>
<br>

<b>Epoch_change_inference output at ending (epoch 44,45,46)</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>
<br>

In this experiment, the training process was stopped at epoch 46 by EarlyStopping callback.<br><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/train_console_output_at_epoch46.png" width="1024" height="auto"><br>
<br>

<a href="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/eval/train_metrics.png" width="520" height="auto"><br>

<br>
<a href="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4 Evaluation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI</b> folder, 
and run the following bat file to evaluate TensorFlowUNet model for AT-Hippocampus-MRI.<br>
<pre>
./2.evaluate.bat
</pre>
This bat file simply runs the following command.
<pre>
python ../../../src/TensorFlowFlexUNetEvaluator.py ./train_eval_infer_aug.config
</pre>

Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/evaluate_console_output_at_epoch46.png" width="1024" height="auto">
<br><br>Image-Segmentation-AT-Hippocampus-MRI

<a href="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_crossentropy) to this <b>AT-Hippocampus-MRI/test</b> was very low, and dice_coef_multiclass very high as shown below.
<br>
<pre>
categorical_crossentropy,0.0064
dice_coef_multiclass,0.9973
</pre>
These scores were improved from the previous evaluation results<br>
<pre>
categorical_crossentropy,0.0278
dice_coef_multiclass,0.9843
</pre>
 in
 <a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI">TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI</a><br>
 .
<br>
<h3>
5 Inference
</h3>
Please move to a <b>./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI</b> folder, and run the following bat file to infer segmentation regions for images by the Trained-TensorFlowUNet model for AT-Hippocampus-MRI.<br>
<pre>
./3.infer.bat
</pre>
This simply runs the following command.
<pre>
python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer_aug.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/mini_test_masks.png" width="1024" height="auto"><br>
<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks of AT-Hippocampus-MRI Images of 256x256 pixels</b><br>
As shown below, the inferred masks predicted by our segmentation model trained by the dataset appear similar to the ,
ground truth masks.
<br><br>
<b> class_color_map = {Anterior:cyan,  Posterior:yellow }</b>
<br><br>
<table>
<tr>
<th>Image</th>
<th>Mask (ground_truth)</th>
<th>Inferred-mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10078.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10078.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10078.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10086.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10086.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10086.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10114.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10114.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10114.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10136.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10136.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10136.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10217.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10217.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10217.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/images/10248.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test/masks/10248.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/AT-Hippocampus-MRI/mini_test_output/10248.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>
References
</h3>
<b>1. DATASET OF MAGNETIC RESONANCE IMAGES OF NONEPILEPTIC SUBJECTS AND TEMPORAL LOBE EPILEPSY PATIENTS 
FOR VALIDATION OF HIPPOCAMPAL SEGMENTATION TECHNIQUES</b><br>
Kourosh Jafari-Khouzani, Kost V Elisevich, Suresh Patel, Hamid Soltanian-Zadeh <br>
<a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC4501402/">
https://pmc.ncbi.nlm.nih.gov/articles/PMC4501402/</a>
<br><br>
<b>2.  Hippocampus Segmentation Using U-Net Convolutional Network from Brain Magnetic Resonance Imaging (MRI)</b><br>
Ruhul Amin Hazarika, Arnab Kumar Maji, Raplang Syiem, Samarendra Nath Sur, Debdatta Kandar <br>
<a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC9485390/">
https://pmc.ncbi.nlm.nih.gov/articles/PMC9485390/</a>
<br><br>
<b>3. Fully Automated Hippocampus Segmentation using T2-informed Deep Convolutional Neural Networks</b><br>
Maximilian Sackl, Christian Tinauer, Martin Urschler, Christian Enzinger, Rudolf Stollberger, Stefan Ropele <br>
<a href="https://www.sciencedirect.com/science/article/pii/S1053811924002647">
https://www.sciencedirect.com/science/article/pii/S1053811924002647</a>
<br><br>
<b>4. TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-MRI
</a>
<br>
<br>
<b>5. TensorFlow-FlexUNet-Image-Segmentation-MSD-Hippocampus</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-MSD-Hippocampus">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-MSD-Hippocampus
</a>
<br>
<br>
<b>6. TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-T1W</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-T1W">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Hippocampus-T1W
</a>
<br>
<br>
<b>7. TensorFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
<br>
<br>
