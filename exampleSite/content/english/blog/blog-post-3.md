---
title: "GAZE DETECTION TUTORIAL"
date: 2022-03-09T11:07:10+06:00
author: ["Zoe White"]
#image : "images/blog/blog-post-3.jpg"
bg_image: "images/feature-bg.jpg"
categories: ["Tutorial"]
tags: ["Research", "How To"]
#description: "this is meta description"
draft: false
type: "post"
---


This project can be found at [this link](https://github.com/charliegerard/gaze-detection).

This tool allows the use of gaze activated software. It would be helpful for me if I wanted to create an interactive piece of art where the user had to move their eyes to interact. I think implementing the body into the interactivity of a project would be a good way to study human-computer interactions. The use of a gaze heat map such as [this one](https://github.com/TobiasRoeddiger/GazePointHeatMap) could also be used to track where a user looks when interacting with a project.

*This tutorial is in Javascript.*

In order to use the gaze detection software we must clone it into our computers using:

```
git clone https://github.com/charliegerard/gaze-detection.git
```

One we have cloned the repository we cn use the software. To start we should have a code file where we want to the code to be. The first thing we should do is import the software:
```javascript
import gaze from "gaze-detection";
```

Load model for machine learning:
```javascript
await gaze.loadModel();
```

The example in the GitHub repository that shows how to set up the software is below. If you are using needs a camera device ID only if you are using something other than your computer's webcam:
```javascript
const videoElement = document.querySelector("video");

const init = async () => {
  // Using the default webcam
  await gaze.setUpCamera(videoElement);

  // Or, using more camera input devices
  const mediaDevices = await navigator.mediaDevices.enumerateDevices();
  const camera = mediaDevices.find(
    (device) =>
      device.kind === "videoinput" &&
      device.label.includes(/* The label from the list of available devices*/)
  );

  await gaze.setUpCamera(videoElement, camera.deviceId);
};
```
This sets up your camera and uses it as input in the software.

Now in this step you can actually add you own code to tell the program what it should do depending on the input it recieves from the camera! The code for this is an 'if statement' and you can designate which direction using 'UP', 'DOWN', 'RIGHT', or 'LEFT'. There are so many cool projects you could create with this software so feel free to expirement!

```javascript
const predict = async () => {
  const gazePrediction = await gaze.getGazePrediction();
  console.log("Gaze direction: ", gazePrediction); //will return 'RIGHT', 'LEFT', 'STRAIGHT' or 'TOP'
  if (gazePrediction === "RIGHT") {
    // do something when the user looks to the right
  }
  let raf = requestAnimationFrame(predict);
};
predict();
```

If you are all done using the gaze detection use this line to stop the detection:
```javascript
cancelAnimationFrame(raf);
```

I hope you enjoyed this tutorial and realized that there are so many cool softwares out there that you can use to make interesting projects!

Here are some other tools I am interested in learning more about:

[Touchdesigner](https://derivative.ca/)

[Blender](https://www.blender.org/)

[Unity](https://unity.com/)