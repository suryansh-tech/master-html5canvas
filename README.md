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

### Creating a preloader function

```javascript
<script>
        //create a frame obj 
        const frames = {
            currentIndex: 0,
            maxIndex: 382
        };

        // loading function
        function preloaderImages() {
            // generated url name for images 
            for(var i=0;i<frames.maxIndex;i++){
                const imageUrl = `./frames/compressed_frame_${i.toString().padStart(4, "0")}.png`
            }
        }
    </script>
```

1. Configure Frame Settings: Modify the frames object to set the currentIndex and maxIndex based on your needs.
2. Preload Images: Call the preloaderImages function to generate the URLs for your images. from **0001 t0 0382**.


