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
[1] Phillip Isola, Jun-Yan Zhu, Tinghui Zhou, and Alexei A. Efros, Image-to-Image Translation with Conditional Adversarial Networks, 2016.  
[2] Jun-Yan Zhu, Taesung Park, Phillip Isola, and Alexei A. Efros, Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks, 2017.  
[3] Taesung Park, Alexei A. Efros, Richard Zhang, and Jun-Yan Zhu, Contrastive Learning for Unpaired Image-to-Image Translation, 2020.
[4] Chunle Guo, Chongyi Li, Jichang Guo, Chen Change Loy, Junhui Hou, Sam Kwong, and Runmin Cong, Zero-Reference Deep Curve Estimation for Low-Light Image Enhancement, 2020.      
[5] {Li-Chongyi/Zero-DCE}(https://github.com/Li-Chongyi/Zero-DCE)  
