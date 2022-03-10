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

In order to use the gaze detection software we must clone it into our computers using:

```
git clone
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



Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ex error esse a dolore, architecto sapiente, aliquid
commodi, laudantium eius nemo enim. Enim, fugit voluptatem rem molestiae. Sed totam quis accusantium iste
nesciunt id exercitationem cumque repudiandae voluptas perspiciatis, consequatur quasi, molestias, culpa odio
adipisci. Nesciunt optio fugiat iste quam modi, ex vitae odio pariatur! Corrupti explicabo at harum qui
doloribus, sit dicta nemo, dolor, enim eum molestias fugiat obcaecati autem eligendi? Nisi delectus eaque
architecto voluptatibus, unde sit minus quae quod eligendi soluta recusandae doloribus, officia, veritatis
voluptatum eius aliquam quos. Consectetur, nisi? Veritatis totam, unde nostrum exercitationem tempora suscipit,
molestias, deserunt ipsum laborum aut iste eaque? Vitae delectus dicta maxime non mollitia? Sapiente eos a quia
eligendi deserunt repudiandae modi molestias tenetur autem pariatur ullam itaque, quas eveniet, illo quam rerum
ex obcaecati voluptatum nesciunt incidunt culpa provident illum soluta. Voluptas possimus nesciunt inventore
perspiciatis neque fugiat, magnam natus repellendus praesentium eum voluptatum, alias incidunt, tempora
reprehenderit recusandae et numquam itaque ratione dolor voluptatibus in commodi ut! Neque deserunt nostrum
commodi dolor natus quo, non vitae deleniti, vero voluptatem error aspernatur veniam expedita numquam amet quia
in dolores velit esse molestiae! Iusto architecto accusantium quisquam recusandae quod vero quia.
