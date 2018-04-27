# HALCON

> "HALCON defines the state of the art in machine vision software. It provides a comprehensive vision library and is always based on the latest and most advanced technology. Whatever your task, HALCON will solve it, fast and with highest accuracy."

#### HALCON’s operators and data structures.

![Basic architecture of HALCON](.gitbook/assets/3drwfbi-dmfzf0o8evmlj.png)

#### **Halcon Parameters and Data Structures:**

* Image
* Regions
* XLDs \(eXtended Line Description\)
* Handles
* Tuple Mode

####  maximum number of parameters:

* iconic input parameters: 9
* iconic output parameters: 9
* control input parameters: 20
* control output parameters: 20

#### Create ROI

For advanced applications `change_domain` can be used as a slightly faster version than `reduce_domain`.This operator does not perform an intersection with the existing domain and does not check if the region is outside the image - which will cause a system crash when applying an operator to the data afterwards if the region lies partly outside the image. If the programmer ensures that the input region is well defined, this is a way to save \(a little\) execution time.

#### Effect of ROI Shape on Speed Up

ROIs are a perfect way to save execution time: The smaller the ROI, the faster the application. This can be used as a general rule. If we consider this in more detail, we also need to think about the shape of ROIs. Because ROIs are based on the HALCON regions they use runlength encoding \(see Quick Guide in section 2.1.2.2 on page 13. for more information on HALCON regions\). This type of encoding is perfect if the runs are long. Therefore, a horizontal line can be both stored and processed more efficiently than a vertical line. This holds as well for the processing time of ROIs. Obviously this type of overhead is very small and can only be of importance with very fast operators like threshold.

#### Filter Image

HALCON offers a wide range of edge filters. One of the most popular filters is the Sobel filter. This is the best of the old-fashioned filters. It combines speed with a reasonable quality. The corresponding operators are called `sobel_amp` and `sobel_dir`.  
In contrast, `edges_image` provides the state of the art of edge filters. This operator is actually more than just a filter. It includes a thinning of the edges using a non-maximum suppression and a hysteresis threshold for the selection of significant edge points. It also returns the edge direction and the edge amplitude very accurately, which is not the case with the Sobel filter. This operator is recommended if higher quality is more important than a longer execution time. If the images are not noisy or blurred, you can even combine accuracy and speed by using the mode `sobel_fast` inside `edges_image`. The corresponding operator to find edges in multi-channel images, e.g., a color image, is `edges_color`.

Here, the parameters are selected such that a non-maximum suppression \(parameter value 'nms'\) and a hysteresis threshold \(threshold values 20 and 40\) are performed. The non-maximum suppression has the effect that only pixels in the center of the edge are returned, together with the corresponding values for the amplitude and the direction. All other pixels are set to zero. Therefore, a threshold with the minimum amplitude of 1 is sufficient here. As a preparation for the next step, the edge contour regions are split up into their connected components.

![\(a\) Extracting edges and \(b\) approximating them by segments.](.gitbook/assets/image%20%281%29.png)

#### Matching

* correlation-based matching
* shape-based matching
* component-based matching
* local deformable matching
* perspective deformable matching
* descriptor-based matching
* 3D matching
* point-based matching

![Overview of the matching process](.gitbook/assets/image%20%282%29.png)

#### Classification

* Multi-Layer Perceptron
* Support Vector Machines
* Gaussian Mixture Models
* K-Nearest Neighbor

