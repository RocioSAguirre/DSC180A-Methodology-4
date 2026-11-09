---
layout: default
---

## About me

- **Name:** Rocio Saez Aguirre
- **Email:** [rsaez@ucsd.edu](mailto:rsaez@ucsd.edu)
- **Section:** Domain 14
- **Mentor:** Siena Okuno and Nathan Hui

## Quarter 2 brainstorming

**1. What is the most interesting topic covered in your domain this quarter?**

The most interesting topic for me was how much the camera itself shapes the data 
before we ever analyze it. Our drone photos are JPEGs with automatic filters on 
them, such as white balance, so this cause each image to be adjusted independently 
from each other that which we have to be cautious of due to the effects it could 
have on our data analysis and processing. I also found that some of the camera's 
own metadata is wrong, like a height field labeled "above sea level" that is actually 
measured from a different reference. This changed how much I trusts the data presented
and made me understand better the process of EDA and data sanity checks. Since 
the colors in a photo are not consistent (auto white balance), the methods 
that rely only on color need to be checked carefully.

**2. Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

Our project is moving from 2D photos into 3D for Quarter 2, so I'd like to investigate 
whether adding 3D shape and height improves how well we can find and outline the individual 
plants we are looking to segment. Besides the drone photos, our lab has 3D point clouds 
built from the overlapping photos, which record the shape and height of plants. 
So, looking into this, one approach we could do would be to take the 2D outlines 
from our Quarter 1 models, like SAM 3, and project them onto the 3D point cloud 
using each photo's GPS position, so we can try to get every plant's 3D shape and height. 
If that works, we can then label those points by species and train a model that works 
directly on the point cloud. I would compare these with our 2D-only models on the same area, 
and see how well each one's predicted plant regions overlap with the labeled ones.
This would show whether 3D information is worth the extra data and computing cost for 
identifying invasive plants.

**3. What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**

I would work from images that already had the 4th NIR band included in the JPEG's embedded data. 
Throughout my research, I found NIR helps immensely to identify vegetation pretty accurately
rather than color based or shape based identifications. It becomes very clear where vegetation
is found and where not, so it would help focus our model to only test on these areas. This
would save computation time and space and help our model be more efficient. I am currently attempting
to get the NIR data from our images in different ways to still get these benefits, so having this already
be recorded in our JPEG's would save a lot of time and give valuable information.

**4. What other techniques would you be interested in using in your project?**

I'd like to try training our models with random color changes, like slightly 
shifting the brightness and white balance of each training image. Since this would 
push the models to rely  more on the shape and texture of plants . I'm also interested in 
few-shot segmentation, where a model learns a new plant type from only a handful of 
labeled examples, since labeling is slow and some species may only show up a few 
times in our photos. Finally, I'd like to try active learning, where the model points out the 
images it is least sure about so we label those first, which could help us get more 
out of a small amount of labeling time.
