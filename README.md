# Filter-Map-Insights

This project aims to visualize filters, feature maps, guided backpropagation from any convolutional layers of all pre-trained models on ImageNet available in `torchvision.models.alexnet`. This will help us observe how filters and feature maps change through each convolution layer from input to output.


### Run on Google Colab
* Go to this link: https://colab.research.google.com/github/nguyenhoa93/cnn-visualization-keras-tf2/blob/master/visualization.ipynb
* Change your runtime type to `Python3`
* Run the code.

![](images/demo-1.gif)

## Briefs

<table style="border-collapse:collapse;border-spacing:0;table-layout: fixed; width: 717px" class="tg"><colgroup><col style="width: 191px"><col style="width: 526px"></colgroup><thead><tr><th style="border-color:inherit;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal"><span style="font-weight:bold">Method</span></th><th style="border-color:inherit;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal"><span style="font-weight:bold">Brief</span></th></tr></thead><tbody><tr><td style="border-color:inherit;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:10px 5px;text-align:left;vertical-align:top;word-break:normal">Filter visualization</td><td style="border-color:inherit;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;text-align:left;vertical-align:top;word-break:normal">Simply plot the learned filters.<br>* Step 1: Find a convolutional layer.<br>* Step 2: Get weights at a convolution layer, they are filters at this layer.<br>* Step 3: Plot filter with the values from step 2.<br>This method does not require an input image.<br><br>
<span style="font-weight:bold;font-style:italic">Alexnet, first conv layer</span>
<p>The size of each filter is 11x11x3, which means that it has a spatial extent of 11x11 pixels and operates on three color channels (red, green, and blue). The filters in this layer are designed to detect low-level features such as edges and corners in the input image, which are important building blocks for recognizing more complex visual patterns.By learning to detect these low-level features, the filters in the first convolutional layer provide a useful representation of the input image that can be used by higher-level layers to recognize more complex patterns</p><img src="https://github.com/mahtaz/filter-map-visualization/blob/main/images/conv0-filters.png" alt="Image" width="500" height="178"><br><br>
<span style="font-weight:bold;font-style:italic">Alexnet, second conv layer</span><p>These filters learn to detect more complex features than the previous layer, such as object parts and textures. The outputs of this layer are also subject to local normalization, which enhances the contrast between neighboring features. The filters in this layer respond to more specific object parts such as eyes, noses, and wheels.</p><img src="https://github.com/mahtaz/filter-map-visualization/blob/main/images/conv1-filters.png" alt="Image" width="500" height="178"><br>
<span style="font-weight:bold;font-style:italic">Alexnet, third conv layer</span><br><img src="https://github.com/mahtaz/filter-map-visualization/blob/main/images/conv2-filters.png" alt="Image" width="500" height="178"><br>
<span style="font-weight:bold;font-style:italic">Alexnet, forth conv layer</span><br><img src="https://github.com/mahtaz/filter-map-visualization/blob/main/images/conv3-filters.png" alt="Image" width="500" height="178"><br>
<span style="font-weight:bold;font-style:italic">Alexnet, fifth conv layer</span><br><img src="https://github.com/mahtaz/filter-map-visualization/blob/main/images/conv4-filters.png" alt="Image" width="500" height="178">
</td></tr>

<tr><td style="border-color:inherit;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:10px 5px;text-align:left;vertical-align:top;word-break:normal">Feature map visualization</td><td style="border-color:inherit;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;text-align:left;vertical-align:top;word-break:normal">Plot the feature maps obtained when fitting an image to the network.<br>* Step 1: Find a convolutional layer.<br>* Step 2: Build a feature model from the input up to that convolutional layer.<br>* Step 3: Fit the image to the feature model to get feature maps.<br>* Step 4: Plot the feature map.<br><br><span style="font-weight:bold;font-style:italic">Alexnet, first conv layer</span><br><img src="https://github.com/mahtaz/Filter-Map-visualization/blob/main/images/layer0-feature-maps.png" alt="Image" width="500" height="394"><br><br><span style="font-weight:bold">Alexnet, 2nd conv layer</span><br><img src="https://github.com/mahtaz/Filter-Map-visualization/blob/main/images/layer1-feature-maps.png" alt="Image" width="500" height="394">
<br><br><span style="font-weight:bold;font-style:italic">Alexnet, 3rd conv layer</span><br><img src="https://github.com/mahtaz/Filter-Map-visualization/blob/main/images/layer2-feature-maps.png" alt="Image" width="500" height="394"><br><br><span style="font-weight:bold">Alexnet, 4th conv layer</span>
<br><img src="https://github.com/mahtaz/Filter-Map-visualization/blob/main/images/layer3-feature-maps.png" alt="Image" width="500" height="394"><br><br><span style="font-weight:bold">Alexnet, 5th conv layer</span>
<br><img src="https://github.com/mahtaz/Filter-Map-visualization/blob/main/images/layer4-feature-maps.png" alt="Image" width="500" height="394"><br><br>
</td></tr>
<tr><td style="border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal" colspan="2">Original image<br><br><img src="https://github.com/mahtaz/Filter-Map-visualization/blob/main/images/dog.jpg" alt="Image" width="720" height="479"></td></tr></tbody></table>

## References
1. [How to Visualize Filters and Feature Maps in Convolutional Neural Networks](https://machinelearningmastery.com/how-to-visualize-filters-and-feature-maps-in-convolutional-neural-networks/) by Machine Learning Mastery
2. [Visualizing Filters and Feature Maps in Convolutional Neural Networks using PyTorch](https://debuggercafe.com/visualizing-filters-and-feature-maps-in-convolutional-neural-networks-using-pytorch/) 
3. CNN visualization with TF 1.3 by [conan7882](https://github.com/conan7882): https://github.com/conan7882/CNN-Visualization

