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
                <!-- here we write canvas -->
            </div>
        </div>
    </div>
```
