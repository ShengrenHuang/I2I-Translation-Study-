# I2I-Translation-Study-

This is the study of image-to-image translation (I2I translation). The concept of I2I translation is to derive an image from an input image retaining the same structure. There exists three main methodologies on this topic: Pix2pix [1], CycleGan [2], and CUT [3]. Here, we study one application of I2I translation upon Pix2pix --- Low light enhancement with zero-reference deep curve estimation [4]. According to [4], the authors employ a deep curve estimation network to gain a best-fitting curve for light enhancement curves from low-light and normal images. The database is unpaired, which avoids the possibility of over-fitting. The cost functions of the learning network are presented as follows (one of the main designs):
1. Spatial Consistency Loss:  
Preserve the different intensities of neighboring regions between input and output. 
2. Exposure Control Loss:  
This loss is to control the image's exposure at a well-exposedness level.
3. Color Constancy Loss:  
Prevent color deviations in the enhanced image.
4. Illumination Smoothness Loss:  
Retain the monotonicity relations between neighboring pixels.

The test and output images through [5] are attached below.




![69 (1) (1)](https://user-images.githubusercontent.com/108604868/195603127-df2b8ad8-551f-4239-bd16-14097238aae8.jpg)


![69 (1) (1)](https://user-images.githubusercontent.com/108604868/195603491-4538a51f-4e25-49ee-bbf3-23d6b92bf4ed.jpg)

## New Idea

Since some output images contain noise-like spots, I believe that we can modify the illumination smoothness loss by taking into account the second derivative or higher derivative on the curve parameter map. That is to say, further improve the illumination smoothness with higher order. We are still working on it.


## References
[1] Image-to-Image Translation with Conditional Adversarial Networks   
[2] Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks  
[3] Contrastive Learning for Unpaired Image-to-Image Translation  
[4] Zero-Reference Deep Curve Estimation for Low-Light Image Enhancement    
[5] https://github.com/Li-Chongyi/Zero-DCE  
