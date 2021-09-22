# Image-Classifier
This project was created jointly by me and a fellow friend in my Electrical Engineering studies Ofek Sharabi (https://github.com/ofek9993)
This classifer uses a neural network trained on the COCO dataset in order to sort photos into common photography generes.

Requirements: 
#####

How to use our program:
We first need to select an input folder that contains the photos we wish to sort, and an output folder in which we sort our photos to
#  ![Alt Text](https://media.giphy.com/media/vFKqnC![ezgif com-gif-maker](https://user-images.githubusercontent.com/88950513/134408823-dc18ece5-f94c-4132-9815-86e88f4ef937.gif)
dLPNOKc/giphy.gif)


While its running we can see our photos being sorted
# GIF 2 תיקיות נוצרות
After all thats done, our program informs us of the unrecognized photos
# GIF 3 UNRECOGNIZED
Here we browse our sorted photos
# GIF 4 לגלוש בתקיות
And the user can also debug photos to see how they were recognized
# GIF 5 DEBUG


How it works:
Our image classifier recives a folder full of images and sorts them by the objects it detects in them.
We use set intersection for our sorting and we go through 3 steps in order to sort our photos:

First step is to go through a list of "Special" cases in the form of tuples, we sort by it if our special case tuple is a subset of our photo's object set.

After that, we go iterate over a dictionary containing diffrenet types of photo idetifier tuples (i.e. Street Photography identifiers, Sports Photography and etc.) and sort by the biggest intersection between our photo's object set and the identifier tuple.

Finally, if we didnt find any match in the first two steps, if we have people in our photo we sort into Portraits, else we put it into unrecogizned folder
