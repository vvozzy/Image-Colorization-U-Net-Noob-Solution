# Image Colorization: U-Net Noob Solution
<i> Image Colorization implementation in PyTorch using U-Net: from Data Preprocessing to Model Training </i>


## Author's Note!
The model presented here was done as final project for my ML training course. Whole code was written by me except adopted block of moving average and [model summary for PyTorch](https://github.com/pytorch/pytorch/issues/2001#issuecomment-405675488). 
The sources I used for creating the project you can find in model notebook or right here after main text body. 
I faced a lot of tricky issues implementing the project (they are discussed below too), so I hope this code will help someone. 
Please, feel free to use the code for your education. Also I'm open to commentaries and suggestions. 
If I make your life easier, please, let me know ;)


## Brief overview 
<p> Notebook <b>Google Colab Pro</b> </p>
<p> Architecture <b>U-Net</b> </p>
<p> Framework <b>PyTorch</b> </p>
<p> Optimizer <b>Adam</b> </p>
<p> Loss <b>MSE</b> </p>
<p> Datasets <b>CIFAR-100, Dogs-vs-Cats</b> </p>


## Notebook
<p> 
I used Google Colaboratory as that was easy and comfortable way for tutor and students to share projects between each other. 
Google Colab gives you 12,5 GB of RAM for free and it's enough if you work with datasets like CIFAR-10 or CIFAR-100. If you want to train your model with a heavier dataset (e.g., Dogs-vs-Cats, CelebA), you need at least about 20 GB of RAM to feel yourself free. Colab Pro provides 25 GB. 
</p> 

## Architecture - U-Net
<p> 
U-Net is a fully convolutional network. It has a u-shape architecture that actually is an encoder-decoder type. U-Net has 31,042,434 parameters, so the training holds from few hours to half of the day depending on the dataset you use. So be patient. 
</p> 

## Framework - PyTorch
<p> 
I lust like it. The end. 
</p> 

## Optimizer - Adam
<p> 
The only true option. SGD and RMSProp slow down training a lot. All the best Image Colorization models use Adam. 
</p> 

## Loss - MSE
<p> 
"Good default choice" for Image Colorization, but actually it's the worst option you can ever imagine. MSE is too straightforward for such comlicated regression task as Image Colorization. It makes model to learn the most popular colours, so the colorized images are usually brownish and greenish. The best choice is custom Loss (weighted Loss) that gives an andvantage to rare colours. Unfourtunately, I didn't have time to try custom Loss for this model. This project is a good exmaple why you should NOT use MSE for Image Colorization.
</p> 

## Datasets
<p> 
Dataset also has impact on sepia effect of colorized images. Colorful datasets are the best choices as you model can learn more colours. 
</p> 
