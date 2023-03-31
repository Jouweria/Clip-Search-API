## Problem Statement
Build video search API that returns all possible videos with a frame having the search
item in it or similar to search item.

## Libraries used
Pytorch, Numpy, Opencv, Flask, Flask_RESTFUL, Pillow, clip

## Dataset
Dataset contains videos along with youtube links

## Implemented Solution
I've extracted and preprocessed each frame from the video and encoded and normalised using clip's "Vit-B/32" model. The frames were then stored for furthur compilation.
For searchng, I have tokenized the input text, then encoded and normalised as done before for each frame and then computed the cosine similarity between each frame and the input text. Then the average of 'N' frames was taken and the cosine similarity above the threshold was checked. Then the result obtained.

For the API, I have used the endpoint as "/clipsearch" and I have taken the input text as parameter using GET method. I then searched the preprocessed data for the given input and then the response is given in json that contains an array of all the youtube links for the videos that contains a frame with the given search item.

## Constants Used
THRESHOLD -> 0.27
NUM OF FRAMES(N) -> 5

## DEMO

![plot](./ScreenShots/.png)