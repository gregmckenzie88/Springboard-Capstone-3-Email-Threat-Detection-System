# Email Threat Detection System 🕵️‍♂️

It's not always easy to know whether a file you've downloaded and are preparing to execute is malicious. How can we be better-prepared to tell the difference between benign and malicious executable files?

Complete notebook [here](https://github.com/gregmckenzie88/Springboard-Capstone-3-Email-Threat-Detection-System/blob/main/notebooks/Email%20Threat%20Detection%20System.ipynb)

## Problem Statement

Emily, owner of Pinnacle Dynamics, is experiencing rapid growth in her business. As much of her business revolves around software being exchanged with her clients via email, she wants to be sure that she is not exposing her system to a virus that may compromise the integrity of her business.

Recently, she has received several portable executable files from a new client that could bring in a lot of business in the coming years. How can she be sure that these files are clean before she responds to him in the next 48 hours?

## The Goal

Create a deep neural network, using Tensorflow, with the intent on classifying image representations of portable executable files (PEs) so that, going forward, we can get a better understanding of the risk in opening files we get from unknown authors.

## Data

To inform these predictions, I pulled data from this [Kaggle competition](https://www.kaggle.com/datasets/matthewfields/malware-as-images)

The 'benign' PEs were pulled from PC Magazine's [The Best Free Software of 2020](https://www.pcmag.com/news/best-free-software). The 'malicious' PEs were pulled from [the zoo](https://github.com/ytisf/theZoo).

Images were generated using [Malook](https://github.com/raynt/mallook), which processes each executable file by converting its data, which is read as a binary stream, into a three-color image, where each piece of data is turned into a color pixel, creating a picture that visually represents the file's contents.

## Data Cleaning

The raw image data arrived in a folder structure like this --

    ├── portable_executables
    │   ├── benign
    │   │   └── lanczos_120
    │   │   └── lanczos_300
    │   │   └── lanczos_600
    │   │   └── lanczos_1200
    │   │   └── nearest_120
    │   │   └── nearest_300
    │   │   └── nearest_600
    │   │   └── nearest_1200
    │   ├── malicious
    │   │   └── lanczos_120
    │   │   └── lanczos_300
    │   │   └── lanczos_600
    │   │   └── lanczos_1200
    │   │   └── nearest_120
    │   │   └── nearest_300
    │   │   └── nearest_600
    │   │   └── nearest_1200

-- where 'benign' and 'malicious' are the classification, 'lanczos' and 'nearest' are distance measurements used to interpret the PE files as images, and the following numerical value represents dots-per-inch.

An image representation of each PE would then be distributed in each of these directories, corresponding to the parameters mentioned above.

These parameters were then used to run experiments on which representation type would yield the best-performing model.

Here is an example of one of these images:

![Raw image](docs/reference-images/raw.png)

I then used OpenCV to trim the axis and enforce dimensions on each image so that each one looked like this:

![Processed image](docs/reference-images/processed.png)
