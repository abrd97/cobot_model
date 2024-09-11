# Glas configuration recognition

This is the repo for preparing the data and training the data for the heart of the complete business logic. In the end we will get a trained model file (in `pth` and `onnx` format) ready to classify the positions of the glasses. It is based on Python Jupyter Notebooks, so you will need to install some packages. I recommend to use a virtual python environment and the embedded Juptyer Notbebook extenstion for VSCode from Microsoft so you can run cell-by-cell inside your editor. It is again based on Python3.10

> Note: This repo contains already the trained model in `pth` and `onnx` format, and the images for the old and new approach. The old approach exists due to completeness. The files with the base name 'best_model_new' are the ones from the new approach

## Approach

The general idea is first to cut the images based on the grid into 15 smaller images sized 117x112 and Use them as the basis for classification. This approach was used because of better training and evluation performances with state-off-the-art classification architectures.

1. `glass_scanner.ipynb`: This was the old approach and still exists for completeness. You can have a look at it but its not recommended to run it because of unclear setup correctness.
2. `images_splitter_new.ipynb`: This notebook file is used for cutting the images and storing it in a seperate folder
3. `training_notebook.ipynb`: The actual data preparation, training, and evaluation including plots

## Setup

create a `python3.10` virtual environment by typing the following command in the terminal:

```bash
python3.10 -m venv .venv
```

activate it:

```bash
source .venv/bin/activate
```

Then install all dependencies by:

```bash
pip install -r requirements.txt
```

Afterwards you can either run

```bash
jupyter notebook
```

in the terminal which will output a link for a webserver running on localhost that will automatically open the brower,

> RECOMMENDED: or you can (after installing the VSCode extension) select the kernel of the virtual environment in the right top corner in the respective notebook file
