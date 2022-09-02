## Project:  Scanning An Image For Probability Of Presence Of Every Alphabet

### Install

This project requires **Python 3.x** and the following Python libraries installed:

- [NumPy]
- [pickle]
- [matplotlib]
- [cv2]
- [pandas]

You will also need to have software installed to run and execute an [iPython Notebook](http://ipython.org/notebook.html)

### Content

Code is provided in the `scanning_an_image_for_probability_of_presence_of_every_alphabet.ipynb` notebook file. 
`data\thresholded` folder contains .csv dataset files specific for each alphabet.
`data\images` folder contains folders specific for each alphabet. each folder contains images of the alphabet it is specific for
`passiveModel` is a persisntent python dictionary holding some results
`test` folder contains images to test on
### project idea
calculation of probability of presence of an alphabet in an image by considering the amount of compatibility of each pixel with each pixel of a collection of images of that alphabet as total

### how it works
-images of each alphabet are converted to samples (records) in .csv files specified for each character (note: .csv files are currently filled)
-data attributes representing an image are the values of each pixel in that image resized, thresholded, and had its white margins trimmed for consistency
-for an alphabet, probability of containing white (1) and probability of containing black (0) in a certain pixel is calculated by looking at number of occurences of (1) and (0) in that pixel in that alphabet data
-calculations for every pixel are done for every alphabet, and results are saved into persistent dictionary called `passiveModel`
-this dictionary is then used at any time to calculate probability of presence of a certain alphabet in an image according to its pixels' values. this is done through mapping each value to the probability of being contained in its pixel for that certain alphabet
-avarage of the probabilities is calculated to formulate the final probability of that certain alphabet to be contained in the whole image
-the method is tested on images located in `test` folder and results are shown in reverse order of probeblilities of all alphabets



### Run

In a terminal or command window, navigate to the top-level project directory `scanning_an_image_for_probability_of_presence_of_every_alphabet.ipynb/` (that contains this README) and run one of the following commands:

```bash
ipython notebook finding_donors.ipynb
```  
or
```bash
jupyter notebook finding_donors.ipynb
```

This will open the iPython Notebook software and project file in your browser.
