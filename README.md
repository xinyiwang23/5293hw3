# 5293hw3
## How to run your code? 
#### Matlab

I implemented the realignment for the ses-test and ses-retest data in Matlab. The corresponding files are in the ‘matlab’ folder (test_realign.m and retest_realign.m). 
The file name test_segmentation.m and retest_segmentation.m are the segmentation part that I generated in Matlab. This step use the realigned image generated in the previous step and create a background mask of the brain. The mask results for these two data are saving in .nii format file and will be using in my python script. 
Note: I choose the 5th tissue which extract the brain regions from the background voxels.
I also realigned ses-test and ses-retest together. The mask image for the extra credit is named as "extra.nii" and will be using in my python script. Also the 5th tissue generated from segmentation part.

#### Python

In my code, first load the labels, ses-test and ses-retest data and their corresponding masks. Then apply the masks and run k-fold cross validation on two datasets separately. Here, I choose the value of k is 5.
For the feature selection, the value of n_component I choosing for PCA is 90.

## Results

For ses-test the best accuracy (only SVM) is 0.9459; the best accuracy (PCA + SVM) is 0.9189.
For ses-retest the best accuracy (only SVM) is 0.8918; the best accuracy (PCA + SVM) is 0.9166.
For extra credit, I only apply SVM and the best accuracy (only SVM) is 0.5108.

https://github.com/xinyiwang23/5293hw3/blob/main/img.png

## Limitation and Improve

Although the accuracy of two dataset with both PCA and SVM are similar, the accuracy of ses-retest data is not as good as the ses-test data (89% vs 94% without PCA). I think one way is to using a better masking threshold to improve the result. The other way is choosing a different tissue to apply mask. Also, Grid Search could be applied to obtain better combination of the paremeters. 

