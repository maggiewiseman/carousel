# Carousel

## See it live
<a href="https://eat-local-pledge.herokuapp.com/" target="_blank">here</a>  and <a href="http://mwiseman.com/projects/carousel/" target="_blank">here

## How it works
Built an image carousel with vanilla JavaScript. Images move every 5 seconds and always appear to come from the right side of the screen. The dots at the bottom allow for the user to navigate to a particular image. The image will still appear to come from the right and the images will continue to animate after 5 seconds starting with the chosen image. The hardest part was getting the right images to slide in and slide out at the right time. It was like herding cats.

In general, manipulation of images is done by adding and removing class names. To get a hold of the images I collected them by Javascript's getElementsByClassName which returns and array of elements that have the requested calss name. 

The way I structured the animation was to have all images have a translateX = 100% so they were off screen on the right. One image had the class "onscreen" which changed the translated property to 0%.  A  5 second setTImeout starts as soon as the image loads and onscreen class is removed and a class of "exit" is added. The exit class has a translateX of -100% so the image will be unseen on the left of the users window. It also has a transition property that causes the change in X position to move at a slower rate. The next image in the queue is given the onscreen class name.

Because there is an event listener listening for the end of the transition event, an event fires and at this point I move the image back to the right by removing the exit class.

The dots at the bottom are clickable. I chose event delegation for this by wrapping the dots in a div and adding the click event listener to the wrapper.  When a dot is clicked the getDotNum function fires.  It loops through the array of dots looking for the dot that has the same id as the event target and then returns the corresponding dot so the "selected" class name can be added to it. 

When a dot is clicked it is important to end the timeout that is currently underway so that you get a full 5 seconds of each image.  This is done by clearing the timeout when a dot is clicked, changing which images is considered the next and then calling the moveImages function again which restarts the animation. 


