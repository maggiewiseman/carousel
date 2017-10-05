# Carousel
Built an image carousel with vanilla JavaScript. Images move every 5 seconds and always appear to come from the right side of the screen. The dots at the bottom allow for the user to navigate to a particular image. The image will still appear to come from the right and the images will continue to animate after 5 seconds starting with the chosen image. The hardest part was getting the right images to slide in and slide out at the right time. It was like herding cats.

The way I structured the animation was to have all images have a translateX = 100% so they were off screen on the right. One image had the class "current" which changed the translated property to 0%.  A  5 second setTImeout starts as soon as the image loads and current class is removed and a class of "end" is added. The end class has a translateX of -100% so the image will be unseen on the left of the users window. It also has a transition property that causes the change in X position to move at a slower rate. 

See it used <a href="https://eat-local-pledge.herokuapp.com/" target="_blank">here</a>  and <a href="http://mwiseman.com/projects/carousel/" target="_blank">here
