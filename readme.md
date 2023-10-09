# 调试日记

原代码运行在python2，现在更改为python3环境，测试能够从test.png文件生成地形并直接启动gazebo显示，不过对于我的四足机器人来说尺度太大了，而且原点太高了我怀疑机器人会卡在下面
如何更改大小和高度：把129 129 12改成33 33 1    0 0 0 改成 0 0 -3

## Terrain Generator

A wizard written in python that helps in creating realistic terrains for *Gazebo* with appropriate textures and lighting.
Terrains are generated using the heightmap provided by the user which is stored either on disk or as a URL.

Heightmaps are basically rasterized images that contain information about *surface elevations*. Using this elevation information we can create beautiful terrains.

<img src="/images/island.png" height=200 width=200>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://image.ibb.co/gafPCT/terrain.png" height=200>

### Working

The wizard basically does the following:

- Asks you simple questions regarding the model
- Resizes the input image to *2<sup>n</sup>+1 x 2<sup>n</sup>+1* pixels and converts it into grayscale
- Creates the model and saves it in your `.gazebo/models` folder
- Creates a `.world` file at the destination path provided by the user

### Requirements

- Python
- Gazebo 7.0 or higher
- lxml
- urllib

### Installation

Install the required files to run on your local system:

- Cloning the repository

      git clone https://github.com/Sarath18/terrain_generator

- lxml

      sudo pip install lxml

- urllib

      sudo pip install urllib
