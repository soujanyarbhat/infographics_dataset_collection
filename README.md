# Infographics - Dataset Creation

Google Drive Link: https://drive.google.com/drive/folders/1JAPL8ZMNFl7CP-gI3cYdCXtI0__api4v?usp=sharing
Scraper reference: https://github.com/geduldig/TwitterGeoPics

### Project structure

The **infographics_dataset_collection** folder has the following structure:

1. code/

a. scraper.ipynb = Notebook to scrape infographics from twitter

b. classifier.ipynb = Notebook to train ResNet50 CNN classifier

c. predictions.ipynb = Notebook to predict labels from test data

2. data/

a. raw/ = Images downloaded from twitter using the scraper

b. train/ = Labeled images('info', 'notinfo')

c. test/ = Unlabeled images

3. models/ = To store trained models used for predictions

a. infographics-classifier.pth = using ResNet50

4. output/

a. predictions.csv = Model predictions in the format (filename, label)

b. info/ = Folder containing all images from the test set labelled as 'info' by the model

5. twitter_auth.conf = Twitter Authentication credentials for scraping (Steps for tokens- https://gist.github.com/varunchaudharycs/2af83ccb19a03265a24c4942e8248c3c)

6. TwitterGeoPics/ = Scraper used

### Dependencies

Packages required:
- numpy
- torch
- torchvision
- Fridge
- tweepy
- pygeocoder
- tzwhere
- TwitterAPI
- os
- csv
- PIL

Environment variables(paths) set in respective notebooks

### Steps

- Run scraper notebook to populate raw data
- Manual labelling of raw data to forumulate train set(segregating images into data/train/info and data/train/notinfo/)
- Run classifier notebook to train classifier on labelled data
- Run predictions notebook to label the unlabelled images in data/test/


published site: https://soujanyarbhat.github.io/infographics_dataset_collection/
