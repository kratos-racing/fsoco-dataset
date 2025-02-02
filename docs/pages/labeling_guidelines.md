---
layout: page
title: Labeling Guidelines
permalink: /labeling_guidelines/
hide: true
---

Thanks for participating in FSOCO! Your contribution will **help other teams** to increase the size of their dataset for cone detection, segmentation and, at the same time, **it will help you** to improve your very own pipeline.  
Combining data from the entire FSD community is a huge challenge as both sensor setups and data quality differ across the teams. Thus, we have to settle on a few ground rules that every submission needs to comply with.

1.  Be consistent! Ensure that your labels adhere to the [guidelines](#guidelines) below.
2.  **Data is king.** Even the most sophisticated approach can only perform as well as the underlying data allows for.
3.  Images, where only half the cones are labeled, will confuse a human learner and a computer alike.
4.  Cones have to adhere to the official FSG rules, e.g., see [here](#classes). You can upload images with non-compliant cones but those annotations will not count towards your contribution.
5.  [Tags](#tags) allow to further analyze the FSOCO dataset
6.  To get started with the supervisely annotation tool, check out this [overview page](https://docs.supervise.ly/labeling/editors/images "Opens in a new tab."){:target="_blank"}.

---
* TOC
{:toc}
---

### Guidelines

|Instruction|Annotation sample|
|--- |:---:|
|Pay attention to **pixel-level accuracy** of the bounding boxes. Please **include the entire base plate**.| <img src="https://i.ibb.co/XJVVMvM/box-base-plate.png" width="200"/>
|Label cones with a segmentation mask that contains the entire cone but is as close to the boundary as possible.<br> **Tip:** Use your mouse wheel to zoom in and the right mouse button to move within the scene. Zooming in allows for you to be more precise with the bitmap brush, while zooming out makes it easier to see if the boundaries are set correctly.| <img src="https://i.ibb.co/qnRZHLg/segmentation.png" width="200" /> |
|Supervisely's [Smart Tool](https://docs.supervise.ly/labeling/editors/images/instruments#smart-tool "Opens in a new tab."){:target="_blank"} is a handy tool for quick and precise segmentation.<br> You simply define a ROI, and foreground (green) and background (red) points, for it to apply the mask itself as can be seen in the example. For better quality, ensure that your images have a good contrast. If there's a lot of [dithering](https://en.wikipedia.org/wiki/Dither "Opens in a new tab."){:target="_blank"} or noise (e.g. high ISO, low exposure) expect it not to work properly. | <img src="https://i.ibb.co/8cDFThz/segmentation-tool.png" width="200" /> |
|**Label all cones in the image that have a defined shape.** A good rule of thumb is to always include areas of more than 100 pixels^2.<br> To the right is an example of a small cone that should be labeled and a cone that is too small and should not be labeled. If your pipeline focuses on cones up to a certain range, you can easily remove very small cones, which are further away, using a simple size-based filter.<br> Segmentation: for such small objects it is advisable to directly use the brush to save time, as the Smart Labeling Tool likely will not work well.| <img src="https://i.ibb.co/y0zv3z8/box-shape-positive.png" width="200"/> <img src="https://i.ibb.co/DYF7CdX/segmentation-shape-positive.png" width="200"/> <img src="https://i.ibb.co/8mytTWJ/guidelines-shape-negative.png" width="200" /> |
|**Label overlapping cones** and tag the overlapped cone as *truncated*. Do not extend the bounding box but only include the visible part of a cone.<br> **Important:** Create **non-overlapping masks** for segmentation. With differing colors, the overlapping masks are easier to spot. If the involved cones are of the same color, zoom in and use a small brush. Overlapping pixels should be less transparent, so it is possible to spot them. We advise to label the cones first as different classes and then change the label afterwards. | <img src="https://i.ibb.co/GJy3FxW/box-overlapping.png" width="200"/> <img src="https://i.ibb.co/Sxd6bsk/segmentation-overlapping.png" width="200"/> |
|**Label cones that are cut off** on the side of an image if you, the human annotator, can clearly identify them.<br> For the same reasons as before, tag them as *truncated*. Pay attention when dealing with orange cones: when you can only see a single stripe, it might be ambiguous whether it is a small or a large cone.| <img src="https://i.ibb.co/X4XLmbG/box-truncated.png" width="200"/> <img src="https://i.ibb.co/tsthQG8/segmentation-truncated.png" width="200"/> |
|**Label cones that are knocked over** and tag them as *knocked_over*.<br>Cones could be knocked-over on purpose, e.g., FSG uses them to separate the track from the preparation area, or because the car touched them in a previous lap. Either way, depending on your setup you might want to filter them out.| <img src="https://i.ibb.co/LRKkB6D/box-knocked-over.png" width="200"/> <img src="https://i.ibb.co/BK1nHbq/segmentation-knocked-over.png" width="200"/> |
|Tag cones that have stickers, e.g., FSG, or whose tape has been removed. Tag them as *sticker_band_removed*.<br>Make sure to only add this tag if you can read the sticker and not only because you know that this image has been taken at FSG. That is, tag the upper cone but do not tag the lower cone.| <img src="https://i.ibb.co/DVSCTt1/tag-sticker-do.png" width="200"/> <img src="https://i.ibb.co/wMhCBS4/tag-sticker-dont.png" width="200"/> |

### Classes
Classes are the same for bounding boxes and segmentation annotations.

|Class|Example|
|---|:---:|:---:|:---:|
|Blue|<img src="https://i.ibb.co/cb9xwV9/class-blue.png" width="150"/>|
|Yellow|<img src="https://i.ibb.co/q0S2XCp/class-yellow.png" width="150"/>|
|Small orange|<img src="https://i.ibb.co/M5fWNp0/class-small-orange.png" width="150"/>|
|Large orange|<img src="https://i.ibb.co/1zsCZTr/class-large-orange.png" width="150"/>|
|Other cone (not rules compliant)|<img src="https://i.ibb.co/rM5TMHc/class-other.gif" width="150"/>|

### Tags
Tags are the same for bounding boxes and segmentation annotations.

|Tag|Example|
| --- |:---:|:---:|
| Knocked over | <img src="https://i.ibb.co/HV4XC3v/tag-knocked-over.png" width="150"/> |
| Tape removed or event sticker | <img src="https://i.ibb.co/gDS7xj8/tag-tape-removed.png" width="150"/> <img src="https://i.ibb.co/NjJFRyd/tag-sticker.png" width="150"/> |
| Truncated | <img src="https://i.ibb.co/WnnGshy/tag-truncated.png" width="150"/> |


### Well labeled images

#### Bounding Boxes

<img src="https://i.ibb.co/vQmvFMd/box-example-1.png" width="1000"/>

<img src="https://i.ibb.co/QYXrzN8/box-example-2.png" width="1000"/>

#### Segmentation

<img src="https://i.ibb.co/RPR21TJ/segmentation-example-1.png" width="1000"/>

<img src="https://i.ibb.co/mcF9qk0/segmentation-example-2.png" width="1000"/>
