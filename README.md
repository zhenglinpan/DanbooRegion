# The DanbooRegion 2020 Dataset[Updated]

<div align="center">

简体中文  |  [English](https://github.com/zhenglinpan/FillLineGaps/blob/master/README_EN.md)

</div>

![img1](https://lllyasviel.github.io/DanbooRegion/page_imgs/ex.jpg)

*- Some example illustration and the corresponding region annotations.*

**原作者: [lllyasviel](https://github.com/lllyasviel)**

**原项目链接: [DanbooRegion](https://github.com/lllyasviel/DanbooRegion)**

Lvmin提供的DanbooRegion基于tensorflow1.5版本，目前(2023.12.28)已经停止维护多年了，许多API已经无法正常使用。

本repo更新了DanbooRegion的环境依赖，并提供了requirements.txt和conda环境文件，用户可以直接安装并正常运行原项目的**Test**代码。

本repo使用tensorflow`1.x`的最后一个维护版本`1.15`，该版本截止至2023.12.28仍可用。

## 安装依赖环境
### 方法1(推荐): 使用conda安装
```bash
conda env create -f environment.yml
```
### 方法2: 使用pip安装(python3.7)
```bash
pip install -r requirements.txt
```

**`重要`**: 在安装完后，由于`keras`和`tensorflow1.15`仍存在一些不太兼容的地方，此时`ai.py[#L58]`处的`load_model()`函数会报错，用户需要手动对这个函数做一些修改。修改方法如下:

1. 跳转到函数定义中(该函数位于keras的安装目录下，`keras/engine/saving.py`)，然后将该文件中所有的`.decode('utf-8')`去掉。

2. 或者用我修改好的`saving.py`直接替换掉该文件也可以。

## 测试代码
按照[DanbooRegion](https://github.com/lllyasviel/DanbooRegion)原项目的指导，运行第九步的测试代码即可正常运行。

```bash
cd ./code/
python segment.py ./emilia.jpg
```

## 测试结果
虽然会跳很多warning出来，但是不影响运行结果，运行结果如下:

![img1](https://github.com/zhenglinpan/DanbooRegion/blob/master/code/results/results.png)