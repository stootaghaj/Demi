# DEMI
## Deep Video Quality Estimation Model using Perceptual Video Quality Dimensions

This repo contains the code to train and test the frame-level DEMI. The code will be updated by mid September 2020.
Please report any problem you faced or suggestion you have to improve the code. 

## Important Note: The model will be updated by end January 2021.

## How to Use
In order to run the code there are two options:
- Test the model on a video, which only the model (path together with name), video path, video name and test type (select video) must be specified. To do so, you can run it as follow:

```
    python test.py 
        --model=./models/subjectiveDemo2_DMOS_UC.model
        --videopath=./videos/ 
        --videoname=sample1.mp4 
        --test_type=video
```

- Test the model based on the extracted frames in nested folders, which requires specifying the model (path together with name), path of the folder that contains folders of frames, image format (e.g. png) and test type (image_folders). 
  -- It is very important to place all folders contain extracted frames in a specific folder. Please follow the example proivded in this repo.   

```
    python test.py 
        --model=./models/subjectiveDemo2_DMOS_UC.model
        --folder=./frames/ 
        --imageformat=png 
        --test_type=image_folders
```

 For more help run:
 ```
    python test.py -h
```

### Output of the model
The current version of model gives you frame level unclearness or blockiness (depends on the selection of model) quality and save it in a csv file. The DEMI follows the MOS score scale, ranging from 1 to 5. The temporal component is missing, but will be added soon. 

### Important Note
- If you run the model for a video (using test_tyep = video), you may get memory error if the video is too lenghty or large. We recommend extracting frames beforehand and use the image-folders mode for testing.
- Please note that the model only predicts the frame quality. The video component is not yet availble. You can simply use average pooling.  
- The code is made for Windows users and it needs revision to use for Linux users.


# Prepration 
Install python and pip, if they are not already installed. Follow the platform specific installation instructions. The following step should be performed to prepare the setup.
```
    git clone https://github.com/stootaghaj/Demi.git 
    pip install -r requirements.txt
```


## Citation 
Please cite the paper below if you use the code or to get more insight about the model:
```
  @inproceedings{Demi,
    title={{DEMI: Deep Video Quality Estimation Model using Perceptual Video Quality Dimensions}},
    author={Zadtootaghaj, Saman and Barman, Nabajeet and Ramachandra Rao, Rakesh Rao and Göring, Steve and Martini, Maria G. and Raake, Alexander and Moeller, Sebastian  },
    booktitle={IEEE Workshop on Multimedia Signal Processing},
    year={2020},
    organization={IEEE},
  }
```


## License 

MIT License

Copyright 2020 (c) Saman Zadtootaghaj.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Contributers 

- [Saman Zadtootaghaj](https://www.qu.tu-berlin.de/menue/team/researchers/zadtootahaj_saman/)


