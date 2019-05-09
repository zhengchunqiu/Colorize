# Colorize



## Git clone and install DeOldify
```
!git clone https://github.com/jantic/DeOldify.git DeOldify
cd DeOldify/
!pip install -r requirements.txt
```

## Colorize image
### Download pretrained weights
```
!mkdir 'models'
!wget https://www.dropbox.com/s/336vn9y4qwyg9yz/ColorizeVideo_gen.pth?dl=0 -O ./models/ColorizeVideo_gen.pth
```
### Colorize
*   **source_url**
Type in a url to a direct link of an image. Usually that means they'll end in .png, .jpg, etc. NOTE: If you want to use your own image, upload it first to a site like Imgur.

*  **render_factor**
The default value of 35 has been carefully chosen and should work -ok- for most scenarios (but probably won't be the -best-). This determines resolution at which the color portion of the image is rendered. Lower resolution will render faster, and colors also tend to look more vibrant. Older and lower quality images in particular will generally benefit by lowering the render factor. Higher render factors are often better for higher quality images, but the colors may get slightly washed out.

*  **How to Download a Copy**
Simply right click on the displayed image and click "Save image as..."!

#### Pro Tips
*  You can evaluate how well the image is rendered at each render_factor by using the code at the bottom (that cell under "See how well render_factor values perform on a frame here").
*  Keep in mind again that you can go up top and set artistic to False for the colorizer to use the 'Stable' model instead. This will often tend to do better on portraits, and natural landscapes.
#### Troubleshooting
If you get a 'CUDA out of memory' error, you probably have the render_factor too high. The max is 45 on 11GB video cards.

```
colorize=get_image_colorizer(artistic=True)

source_url='https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557392891983&di=205c7b4da7dae284835db01d24d02ece&imgtype=0&src=http%3A%2F%2Fimg.ph.126.net%2FaNbwp33Ay72hovYDHLEhwg%3D%3D%2F1002332392083452398.jpg' #@param {type:"string"}
render_factor=35 #@param {type:"slider",min:7,max:45}

if source_url is not None and source_url !='':
  imgage_path=colorize.plot_transformed_image_from_url(url=source_url,
                                                       render_factor=render_factor,
                                                       compare=True)
  show_image_in_notebook(image_path)
else:
  print('Provide an image url and try again.')
```




## Colorzie video
```
!mkdir 'models'
!wget wget https://www.dropbox.com/s/zkehq1uwahhbc2o/ColorizeArtistic_gen.pth?dl=0 -O ./models/ColorizeArtistic_gen.pth
```

