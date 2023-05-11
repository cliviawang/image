# Image compositor for Stable Diffusion WebUI

Using this plugin, you can perform cropping and stitching on a single page, and generate a base map for Controlnet. The traditional method requires the use of two to three different software programs to switch back and forth, but this tool greatly simplifies the process.

# Installation
1: Install the ControlNet plugin
2: Download this plugin to the ${sd-webui}/extensions directory

Note: The plugin needs to restart sd-webui for the first use to install the rembg library, rather than restarting the UI.

## How to Use
The general usage process of this plugin is as follows:
1: Collect the required image elements that need to be spliced together
2: Place the elements that need to be spliced together on the canvas
3: Convert the canvas into a semantic map
4: Use Controlnet and the semantic map to generate a new image.
The following describes each step in detail:

### Step 1:

Use the remove background function to extract the main elements from the image. As shown in the figure below, we uploaded a picture of a girl walking on an arched road in the Source box, and then obtained a girl walking from the processed box. We used the same method on the right to obtain a car
![girl Image](https://git.woa.com/cliviawang/sd-webui-image-compositor/blob/1230bee93ea716bbf8c42db1c8083d1b8d8a9d02/girl.png) ![car Image](https://git.woa.com/cliviawang/sd-webui-image-compositor/blob/1230bee93ea716bbf8c42db1c8083d1b8d8a9d02/car.png) 

### Step 2:

Integrate multiple elements onto the canvas and convert them into a semantic map. As shown in the figure below, we first added a picture of a night city street as the background to the canvas (Add Background To Canvas button), then sent the girl and car to the canvas (Send to canvas button), and adjusted their size and position so that they looked more natural on the street. Finally, we converted the entire canvas into a semantic map (Segmantic Recognition button)
![image_seg Image](https://git.woa.com/cliviawang/sd-webui-image-compositor/blob/1230bee93ea716bbf8c42db1c8083d1b8d8a9d02/image_seg.png) 

### Step 3:

Send the semantic map to Controlnet (Send to txt to image button), then enable Controlnet and select control_sd15_seg as Model and none as Preprocessor
![image_con Image](https://git.woa.com/cliviawang/sd-webui-image-compositor/blob/1230bee93ea716bbf8c42db1c8083d1b8d8a9d02/image_con.png) 

### Step 4:

Enter suitable prompts and generate the image.
![image_done Image](https://git.woa.com/cliviawang/sd-webui-image-compositor/blob/1230bee93ea716bbf8c42db1c8083d1b8d8a9d02/image_done.png) 