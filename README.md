# Nuclei_segmentation_Unet
This is a project for nuclei segmentation using residual Unet and MIScnn framework committed by @muellerdo where I changed subfunctions so that it works with newest versions of imported libraries.

Here I did a pipeline for nuclei instance segmentation for 2d images using residual Unet. As Unet is able to do only a semantic segmentation, I modified masks so that Unet predicts not only areas where nuclei are located but also the borders between sticked-together nuclei (this idea I found in discussion of 1st place team solution on 2018 data science bowl on Kaggle: https://www.kaggle.com/competitions/data-science-bowl-2018/discussion/54741). 

This idea did not work so well, so I tried an additional approach in postprocessing, using ComputerVision. I chose those contours which had a low convexity and found points where convexity defect is maximal, which probably are starting points of a border between nuclei. But this approach would work only in case of two sticked-together nuclei (like in my data).
