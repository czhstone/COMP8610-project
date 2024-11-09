<img src="/demo.jpg" alt="image alt" style="max-width: 100%; height: auto;">

First and third columns: 3D geometries generated without the shape-aware initialization. Second and fourth columns: result of utilizing shape-aware initialization. The prompts used for generating these images, arranged from left to right and top to bottom, are as follows: “The Leaning Tower of Pisa,” “A baseball bat,” "A sports car," "A gaming controller," "A keyboard," and "A mobile phone"



### Usage:

In the threestudio project, you can find a file named z-temp.ipynb

To test shape aware initialization, you can use generate_normalized_init_params function to get a xyz value, then run:
```
!python launch.py --config configs/fantasia3d.yaml --train --gpu 0 system.prompt_processor.prompt="The leaning tower of Pisa" system.geometry.shape_init=ellipsoid system.geometry.shape_init_params="[x, y, z]"
```

To run the baseline(without shape aware initialization):
```
!python launch.py --config configs/fantasia3d.yaml --train --gpu 0 system.prompt_processor.prompt="The leaning tower of Pisa"
```
(you can replace "The leaning tower of Pisa" with your own prompt)

This phase is trained on a RTX 4090 GPU, takes around 30-40mins(Varies according to prompt used) 


The code is built based on [threestudio project](https://github.com/threestudio-project/threestudio).





