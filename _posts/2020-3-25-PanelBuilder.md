---
layout: post
title: UHD 2Si or SQD?
---
What is 2si? What is SQD? What is better or worse?


## What is SQD? ##
Square Division consists to divide the picture in four equal sub-pictures called quadrants,
ABCD and to create for each quadrant a 1080 progressive picture that will be coded in a
3G serial interface format.

+ The first Quad Link method introduced to produce a UHD image
+ Each link contains one quarter of the original image
+ Each quarter image is displayed at HD 1920 x1080 resolution
+ All four quarters are then reassembled to create a full UHD image

![an image alt text]({{ site.baseurl }}/images/sqd.png "sqd")


## What is 2SI ##
2 Sample Interleave -  This is completely different and consists to put the two first samples of the first
line on link A, then the two next in link B and to repeat this process over the line 1. Then
line two of the picture will be divided exactly the same but put in links C and D, and
identically for even and odd lines alternatively

+ Each quad shows the same image at 1920 x 1080 resolution
+ Each quarter image focuses on certain pixels of the image
+ The four ¼ images are then combined to create a 3840x2160 image

![an image alt text]({{ site.baseurl }}/images/2sia.png  "2si")

### Advantages ###
The inconvenient of SQD is that if one link is missing, then it makes a quarter of the
picture black. It also requests a lot of memory to store at least two of the 4 links to display
the picture correctly. It also requests a perfect timing to align the images.

Nevertheless, it is much simpler to put in place. SQD is used in post-production and in small systems.


The advantages of the 2SI is that a loss of one of the cable is not blanking a quarter of
the image, it just results in a loss of resolution. Also note that the link 1 only is a kind of
down-conversion from 4K to HDp. The data multiplex is/was very complex, but it needs a
simpler memory configuration and then gives a less processing delay. 2SI is used for
encoding and transmission applications.


![an image alt text]({{ site.baseurl }}/images/2si.png "compare 2si and sqd")


## What is the best option?? ##
The short answer- 2 Sample Interleave. While Square Division Quad was originally the easiest solution for transporting the camera’s signal, it causes many inefficiencies when the quad link signals enter your production switcher.
