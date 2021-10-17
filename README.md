# (wip) darlene-sg3

> Those who do not want to imitate anything, produce nothing.
- Salvador Dali

> You stole from me, but I stole from you first.
- Darlene Alderson

Code for running inference and interpolation on a stylegan3 trained on synthetic data.

How much can we learn about a model from its generations? DALL-E from OpenAI still isn't released and it doesn't look like that's going to happen anytime soon. We do, however, have roughly a million generations from DALL-E covered under Creative Commons available from OpenAI's CDN. 

I'm currently training a stylegan3 on the synthetic image dataset from OpenAI's DALL-E generations. Just a little experiment as I only have access to a single RTX 2070 Super for training. There are 1.1 million of them. Conveniently, there are 32 images for each given caption and they are all reranked using CLIP ViT-L/14 (unreleased) from 512 total generations (not included). Using a batch size of 32, this gives strong guarantees about the distribution of the dataset and can hopefully help with some of the stability issues with GAN training. 

The largest subset of images is the mannequins, showing a vast array of outfits on 128,000 male mannequins and 128,000 female mannequins. I hope this means the StyleGAN3 can learn plenty about fashion. Another large subset is drawings and illustrations which I'm curious to see personally with the strange pixel-less nature of StyleGAN3. 

Training on a single GPU is tough - but I hope it's becoming more feasible. This repository is also meant to test those limits specifically as the current GPU situation is problematic for the democratization of applied machine learning. 


This code is licensed under MIT unless (and, I am not a lawyer) breaking the terms outlined in the nvidia stylegan3 repository; which essentially automatically gives them ownership over anything trained with it as far as I can tell and prevents commercial use (unless it's for them, of course).

I would eventually also like to compare the performance on this dataset with the clean room implementation of alias free gan "rosinality" which as far as I can tell is not at all restricted by the terms laid out in stylegan3 as it was implemented before the code was released.
