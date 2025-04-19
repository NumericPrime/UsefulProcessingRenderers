# UsefulProcessingRenderers

This library contains (currently) two new renderers for Processing.

## The Overlay Renderer
### Overview
The Overlay Renderer allows creating an overlay using processing. It works by creating an invisble window on wich one can paint using processing.

One can use the program below except if you click on something drawn with the renderer. There is an option that one can click on the window below regardless.

There is an issue with MacOS where this doesn't work. The overlay will properly render however the window below can't be interacted with because a bug in the JDK.

### Usage
When calling size one can access the overlay renderer the follwing way:

```java
size(100,100,usefulrenderers.UsefulRenderers.OVERLAY)
```

any arguments passed for window-size will be ignored.
The background command will still paint the whole screen. Calling background(0,0,0,0); will fill the screen with transparent pixels allowing seeing and using the program below. 

Analogously calling fill(0,0,0,0); and stroke(0,0,0,0); will make outline/inside of a shape be drawn with transparent pixels.

Having only filling with transparent pixels active will make the outline not be drawn and vice versa.

Calling setCursor(-1); Will toggle the option to allow interacting with the window below even when clicking on a shape.
## The No-Window renderer
### Overview
This, as the name implies prevents processing from opening a window when starting the sketch. Normaly one uses getSurface().setVisible(false); to do this. However the window can be seen for a split-second and there is still overhead when starting the sketch from creating the window.
### Usage
As with the last renderer one can put the renderer in the third argument when calling size.

```java
size(100,100,usefulrenderers.UsefulRenderers.NOWINDOW)
```

Since no window will be created anything inputted into size will not have any effect on the program.
