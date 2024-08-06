# master-html 5 canvas

## What is CANVAS
#### HTML5 Canvas is a feature of HTML5 that allows users to draw 2D shapes and bitmap images, interact with graphics on a page, and create animations

- in this we learn a scrollbased animtion of html 5 for making this effect we need some stuff
1. Frames [images]
2. green sock animation library
3. love
4. ffmpeg software

# lets start 👌

## installisition part

# Lets Code baby

as we want the animation happens on scroll based. so 1st we make a scroller div warpped with a parent. this scroller div is always sticky and scrolls over the parent div

image 1
image 2

```html
    <div class="w-full h-screen bg-zinc-900">
        <div class="parent relative top-0 left-0 w-full h-[700vh] bg-zinc-800">
            <div class="w-full sticky top-0 left-0 h-screen bg-red-500">
                <!-- here we write canvas having id and covers full screen-->
                 <canvas class="w-full h-screen" id="frame"></canvas>
            </div>
        </div>
    </div>
```

```html
<div class="w-full sticky top-0 left-0 h-screen bg-red-500">
```

`👁️ this will stick our scroller div to screen height so when we scroll its move over the wrapper which is 700vh height`

## PRELOADER 😎
As we have a bunch of images nearly [382] so we want that these images load first before scrolling its a good practice other wise our animation is laggy

### 1. Creating a preloader function

```javascript
<script>
        // create a frame obj 
        const frames = {
            currentIndex: 0,
            maxIndex: 382
        };

        // loading function
        function preloaderImages() {
            // generated url name for images 
            for(var i=0;i<=frames.maxIndex;i++){
                const imageUrl = `./frames/compressed_frame_${i.toString().padStart(4, "0")}.png`
            }
        }
    </script>
```

1. Configure Frame Settings: Modify the frames object to set the currentIndex and maxIndex based on your needs.
2. Preload Images: Call the preloaderImages function to generate the URLs for your images. from **0001 t0 0382**.

image 3

### 2. Creating IMG Tag and stores the src further we will check all images are loaded or not:

image 4

- Now inside loader funtion we make a new image and store the src into img tag from **0001 t0 0382** 

```javascript
<script>
        //create a frame obj 
        const frames = {
            currentIndex: 0,
            maxIndex: 382
        };

        // tracking how many images are loaded
        let imagesLoaded = 0;

        // loading function
        function preloaderImages() {
            for(var i=0;i<=frames.maxIndex;i++){
                const imageUrl = `./frames/compressed_frame_${i.toString().padStart(4, "0")}.png`;
                const img = new Image();
                img.src = imageUrl;
                //on loading images 
                img.onload = () =>{
                    imagesLoaded++;
                    if(imagesLoaded === frames.maxIndex) {
                        console.log("all images are loaded")
                    }
                }
            }
        }

        preloaderImages();
    </script>
```

#### Here's a breakdown of how it works:

1. Create Image Objects: For each URL, it creates a new Image object and sets its src attribute to the generated URL. This triggers the browser to start loading the image.
2. Track Loaded Images: It adds an onload event listener to each image. When an image successfully loads, it increments the imagesLoaded counter.

- Check Completion: After incrementing the counter, it checks if the number of images loaded (imagesLoaded) matches the total number of images (frames.maxIndex). If so, it logs a message to the console indicating that all images have been loaded.

#### 3. after loading all the images we save the img tag into the array

```javascript
// from previous code 
const imageUrl = `./frames/compressed_frame_${i.toString().padStart(4, "0")}.png`;
const img = new Image();
img.src = imageUrl;
```
we have to save these images into the array 

```javascript
// creating array of images
        const images = [];
```
then after loading each img one by one we pust into the array

```javascript
//on loading images 
img.onload = () =>{
    imagesLoaded++;
    if(imagesLoaded === frames.maxIndex) {
        loadImage(frames.currentIndex);
    }
}
images.push(img); // saving images into images array variable
```

## LoadImage() 

```javascript
//LoadImage funtion logic
        function loadImage(index){
            if(index >= 0 && index <= frames.maxIndex) {}
        }
```        
- checks whether a given index is within the valid range of image and its index should be positive         
        



