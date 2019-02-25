# ObjectDetection
This is a repo for researching object detection tricks

# Learning Notes
### 2019-02-25 
[Notes1](https://www.cnblogs.com/MY0213/p/9460562.html)
[Notes2](https://segmentfault.com/a/1190000016138673)
RCNN->SppNET->Fast-RCNN->Faster-RCNN
1. Region Proposal method
1.1 Sliding Window(brute force)
Use windows with different size to scan the imgae from up to donw, left to right
pseudocode：
```python
for window in windows:
	patch = fetch_patch(image, window)
	results = detector(patch)
```
1.2 Selective Search
region proposal method
ROI region of interest
[selective search Paper](http://www.huppelen.nl/publications/selectiveSearchDraft.pdf) [Notes](https://blog.csdn.net/guoyunfei20/article/details/78723646)
[Graph-Based Image Segmentation Paper](http://people.cs.uchicago.edu/~pff/papers/seg-ijcv.pdf) [Notes](https://blog.csdn.net/guoyunfei20/article/details/78727972)

Firstly, form some regions using color similarity. 
details: treat each image as a non-direction graph, distance between vertices are distance between pixels(I prefer HSV rather than RGB here). We set a Threshold to find MSTs(Minimum Spanning Tree) from them to form initial ROIs.

Then, we merge ROIs again based on  
color similarity, 
texture similarity,
size similarity,
shape compatibility measure,

		 
1.3 R-CNN

