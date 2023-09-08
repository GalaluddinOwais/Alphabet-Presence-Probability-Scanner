## Project:  Scanning An Image For Probability Of Presence Of Every Alphabet

### Install

This project requires **Python 3.x** and the following Python libraries installed:

- NumPy
- pickle
- matplotlib
- cv2
- pandas

you will also need to download the following .zip files
- [.csv datasets for each alphabet](https://drive.google.com/file/d/1R-xO2VFmfdvSZcZRTiaQ39kOBwTJ5Igd/view?usp=sharing) (extract it to `data\thresholded` folder )
- [folders of images specific for each alphabet](https://drive.google.com/file/d/1P9Nuhanv9i-cgG10_PeMcp3pxeBpM1mf/view?usp=sharing) (extract it to `images` folder )

You will also need to have software installed to run and execute an [iPython Notebook](http://ipython.org/notebook.html)

### Content

- Code is provided in the `scanning_an_image_for_probability_of_presence_of_every_alphabet.ipynb` notebook file.
- `data\thresholded` folder contains .csv dataset files specific for each alphabet.
- `images` folder contains folders specific for each alphabet. each folder contains images of the alphabet it is specific for
- `passiveModel` is a persisntent python dictionary holding some statistical results
- `test` folder contains images to test on

### project idea
calculation of probability of presence of an alphabet in an image by considering the amount of compatibility of each pixel with each pixel of a collection of images of that alphabet as total

### how it works
- images of each alphabet are converted to samples (records) in .csv files specified for each character (note: .csv files are currently filled)
- data attributes representing an image are the values of each pixel in that image resized, thresholded, and had its white margins trimmed for consistency
- for an alphabet, probability of containing white (1) and probability of containing black (0) in a certain pixel is calculated by looking at number of occurrences of (1) and (0) in that pixel in that alphabet data
- calculations for every pixel are done for every alphabet, and results are saved into persistent dictionary called `passiveModel`
- this dictionary is then used at any time to calculate probability of presence of a certain alphabet in an image according to its pixels' values. this is done through mapping each value to the probability of being contained in its pixel for that certain alphabet
- average of the probabilities is calculated to formulate the final probability of that certain alphabet to be contained in the whole image
- the method is tested on images located in `test` folder and results are shown in reverse order of probablilities of all alphabets, and it shows the correct alphabet detected for 26 images out of 28 when considering the alphabet of the highest probability as the alphabet detected






### Run

In a terminal or command window, locate `scanning_an_image_for_probability_of_presence_of_every_alphabet.ipynb` and run one of the following commands:

```bash
ipython notebook scanning_an_image_for_probability_of_presence_of_every_alphabet.ipynb
```  
or
```bash
jupyter notebook scanning_an_image_for_probability_of_presence_of_every_alphabet.ipynb
```

This will open the iPython Notebook software and project file in your browser.
