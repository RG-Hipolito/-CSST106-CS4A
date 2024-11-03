# Documentation


## Midterm Project: Implementing Object Detection on a Dataset
### By: Regina Grace Hipolito

* I chose HOG as I found it the easiest to work with.
* I downloaded a butterfly species dataset I found on Kaggle
* https://www.kaggle.com/datasets/gpiosenka/butterfly-images40-species/data

### Data Processing
* I changed the "filepaths" column's content in order to make it readable by the code.
* Added "/content/drive/MyDrive/" before every data in the "filepaths" column.
* Saved the updated .csv file.

### HOG Training
* I used the HOG Traditional method.
* Added a progress bar.
* Processed 13594 images.
  
Results:
 * Accuracy: 0.38543582199337995
* Precision: 0.4013127708007508
* Recall: 0.38543582199337995
* Average Detection Time per Image: 0.08271707534790039 seconds

### Saved the Model
* Directly to my google drive as a failsafe.

### Predictions
* The model cannot read color, so silhouettes and greyscale comparisons are it's ability.
* Tested with Adonis, Rosy Maple Moth and Cleopatra butterflies
* Was able to correctly predict the Cleopatra.
* Adonis Butterfly was incorrectly predicted as Black Argus.
* Rosy Maple Moth was incorrectly predicted as Humming Bird Hawk Moth
  
