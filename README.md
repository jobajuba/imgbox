# ScaleAPI - Image Annotation MVP

## Setup

To set up, clone the repository
```
git clone https://github.com/JohnnyJohnAndTheFunkyBunch/imgbox.git
```
Then install the packages and run `server.js`

```
npm install
node server.js
```

## Using the web app
The server should be served on port `8080`. You can then open the web app through `[your ip address]:8080` and it should look something like this:

![alt text](Doc/image1.png)

## Using the annotation API entry point
Just like the real ScaleAPI, you curl using these parameters:
```
curl "http://[your ip address]:8080/api/task/annotation" \
  -u YOUR_API_KEY: \
  -d callback_url="http://www.example.com/callback" \
  -d instruction="Draw a box around each baby cow and big cow." \
  -d attachment_type=image \
  -d attachment="http://i.imgur.com/v4cBreD.jpg" \
  -d objects_to_annotate="baby cow" \
  -d objects_to_annotate="big cow" \
  -d with_labels=true
```

## Features that might not be obvious
* Picture scale automatically to fit the webpage, bounding boxes are still in reference to the orginal image size
* Press R for reset
* Press Space or Enter to submit
* Press Broken to write a message to why the task is invalid
* You can click on an image on "Up Next" to change image to work on
* You can sort by urgency or creation date

## Features to implement
* Color code the bounding boxes depending on the object
* Annotated image page to see all the images annotated
* Session information
* Be able to delete annotations through Annotations Box
* Better feedback on submit to feel like you did something great
