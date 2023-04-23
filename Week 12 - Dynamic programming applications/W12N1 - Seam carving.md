**Seam carving** is an approach for resizing images by removing or duplicating **seams** (a connected sequence of pixels running from top-to-bottom or left-to-right across an image). This avoids some of the distortion caused by scaling, and avoids the loss of information from cropping.

For resizing an image, we want to find low energy seams, where there is little difference between seam pixels and their neighbours.

# Building a seam
When we construct a seam, we can select either the pixel directly below, one pixel left, or one pixel right of the current tip of the seam.
As we want to find low energy seams, we need an **energy function**, which calculates the energy of a pixel in some way.

The energy function is often a gradient score.
