# The DanbooRegion 2020 Dataset[Updated]

<div align="center">

[简体中文](https://github.com/zhenglinpan/DanbooRegion/blob/master/README.md)  |  English

</div>

![img1](https://lllyasviel.github.io/DanbooRegion/page_imgs/ex.jpg)

*- Some example illustration and the corresponding region annotations.*

**Original author**: [lllyasviel](https://github.com/lllyasviel)

**Original project link**: [DanbooRegion](https://github.com/lllyasviel/DanbooRegion)

The DanbooRegion provided by Lvmin is based on the TensorFlow 1.5 version, which has been discontinued for many years (as of December 28, 2023). Many APIs are no longer functioning properly.

This repo updates the environment dependencies of DanbooRegion and provides requirements.txt and conda environment files. Users can directly install and run the Test code of the original project.

This repo uses the last maintenance version of TensorFlow 1.x, '1.15', which is still available as of December 28, 2023.

## Installing Dependent Environments
### Method 1 (recommended): Install using conda
```bash
conda env create -f environment.yml
```

### Method 2: Install using pip (python3.7)  
```bash
pip install -r requirements.txt
```

**`IMPORTANT`**: After installation, due to some incompatibilities between `keras` and `tensorflow1.15`, the `load_model()` function at `ai.py[#L58]` will raise an error. Users need to manually make some modifications to this function. The modification method is as follows:

Jump to the function definition (the function is located in the installation directory of Keras, `keras/engine/saving.py`), and remove all the `.decode('utf-8')` in the file.

Alternatively, you can directly replace the file with the modified `saving.py` provided in this repo.

## Testing
Follow the instructions in the original DanbooRegion project to run the test code in `step 9`.

```bash
cd ./code/  
python segment.py ./emilia.jpg
```

## Results
Albeit some noticiable warnings, the code shall funtion normally, here's my test results:

![img1](https://github.com/zhenglinpan/DanbooRegion/blob/master/code/results/results.png)

