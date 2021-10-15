# max-lens-radius
This project provides source code to accompany the paper: 

Matthew J. Leotta, David Russell, Andrew Matrai,
"On the Maximum Radius of Polynomial Lens Distortion",
Winter Conference on Applications of Computer Vision (WACV) 2022.

## Paper Abstract
> Polynomial radial lens distortion models are widely used in image processing
and computer vision applications to compensate for when straight lines in the
world appear curved in an image. While polynomial models are used pervasively
in software ranging from PhotoShop to OpenCV to Blender, they have an often
overlooked behavior: polynomial models can fold back onto themselves.
This property often goes unnoticed when simply warping to undistort an image.
However, in applications such as augmented reality where 3D scene geometry is
projected and distorted to overlay an image, this folding can result in a
surprising behavior. Points well outside the field of view can project into
the middle of the image. The domain of a radial distortion model is only valid
up to some (possibly infinite) maximum radius where this folding occurs.
This paper derives the closed form expression for the maximum valid radius and
demonstrates how this value can be used to filter invalid projections or
validate the range of an estimated lens model.  Experiments on the popular
Lensfun database demonstrate that this folding problem exists on 30\% of lens
models used in the wild.


[Data](data/lensfun_data.csv) used in the experiments was collected from the
[Lensfun](https://lensfun.github.io/) project in the Spring of 2021.

The algorithm in this paper has been incorporated into the camera models in
Kitware's [KWIVER](https://github.com/Kitware) code base.  Specifically,
you can find the C++ implementation
[here](https://github.com/Kitware/kwiver/blob/v1.6.0/vital/types/camera_intrinsics.cxx#L301).
