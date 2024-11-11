## I2-HOFI
The official source code for *"Interweaving Insights: High-Order Feature Interaction for Fine-Grained Visual Classification (FGVC)"*, implementing advanced FGVC with high-order feature interactions through Graph Neural Networks (GNNs).

![Visualization of I2-HOFI](media/I2hofi_visualization.gif)

## Introduction
This repository implements a novel approach to FGVC using GNNs for advanced feature interactions. By constructing inter- and intra-region graphs, our method combines global and local features to enhance visual pattern recognition. Using shared GNNs with an attention mechanism and the APPNP algorithm, our approach optimizes information flow, boosting model efficiency and stability with residual connections. Achieving state-of-the-art results on FGVC benchmarks, this work highlights GNNs' potential in capturing complex visual details.

### Link to the Paper
You can access the full paper here : [Interweaving Insights: High-Order Feature Interaction for Fine-Grained Visual Recognition](https://link.springer.com/article/10.1007/s11263-024-02260-y)

### Upcoming Updates
We're preparing to release several enhancements soon:
- Pre-trained model weights trained on different the datasets to facilitate result reproduction.
- An inference script for reproducing the results.
- Releasing t-SNE plotting code for visualization and analysis of model outputs.

## Installation Guide

### Prerequisites
Ensure you have Python 3.9+ installed on your system. You can download it from [Python's official website](https://www.python.org/downloads/).

### Virtual Environment Setup (Recommended)
For setting up a virtual environment, we recommend using [Anaconda](https://www.anaconda.com/download) to manage dependencies efficiently. Anaconda simplifies the process of creating isolated environments through `conda` and ensures compatibility across packages. To get started, run the following commands in your console:

#### Installation on Linux
1. **Create and activate a new Conda environment:**
   ```bash
   conda create -n myenv python=3.9
   conda activate myenv
   ```

2. **Install TensorFlow with CUDA support (if using GPU):**
   ```bash
   pip install tensorflow==2.12.1
   ```

3. **Verify the TensorFlow installation with CUDA support:**
   ```bash
   python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   ```
   If the tensorflow is not able to detect CUDA devices try perform this optional installation:
   ```bash
   pip install cuda-python
   ```

4. **Install other necessary packages:**
   ```bash
   pip install opencv-python
   pip install spektral
   pip install wandb
   ```

#### Installation on Windows

1. **Create a new Conda environment with basic packages from the Anaconda channel:**
   ```bash
   conda create -n myenv anaconda python=3.9
   ```

2. **Activate the Conda environment:**
   ```bash
   conda activate myenv
   ```

3. **Install GPU support packages:**
   ```bash
   conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
   ```

4. **Install TensorFlow (version compatibility with GPU on Windows):**
   Note: TensorFlow versions above 2.10 are not supported on the GPU on Windows natively.
   ```bash
   python -m pip install "tensorflow<2.11"
   ```

5. **Verify TensorFlow installation with GPU support:**
   ```bash
   python -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   ```

6. **Install other necessary packages:**
   ```bash
   pip install opencv-python spektral wandb
   ```

---------------------------------













   

#### Installation on Windows
1. **Create  a new Conda environment with basic packages from anaconda channel:**
   ```bash
   conda create -n myenv anaconda python=3.9
   ```
2. **Activate a Conda environment**
   ```bash
   conda activate myenv
   ```
3. Install necessary packages to run on gpu
    ```bash
   conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
   ```

4. Install tensorflow. Please note Anything above 2.10 is not supported on the GPU on Windows Native
   ```bash
   python -m pip install "tensorflow<2.11"
   ```

5. Verify installation
   ```bash
   python -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   ```

6. **Install other necessary packages:**
   ```bash
   pip install opencv-python
   pip install spektral
   pip install wandb
   ```









------------------------


This setup will prepare your environment with the necessary libraries to run the project. Please ensure that TensorFlow with CUDA support is correctly installed. 
- If you encounter issues installing TensorFlow with CUDA, which may occur due to hardware differences, please refer to the official [TensorFlow installation guide](https://www.tensorflow.org/install/pip) for detailed instructions. We recommend installing a specific version of TensorFlow to prevent compatibility issues, as newer versions may introduce changes that could lead to errors in our code. For optimal performance, a GPU with a minimum of 16GB of VRAM (dedicated memory) is recommended.

- It's also recommended to use Weights & Biases (WandB) for tracking metrics such as training and validation accuracy. Start by creating a WandB account and obtaining your API key following [quickstart guide](https://docs.wandb.ai/quickstart). In the `./configs/config_<dataset_name>.yaml` file, locate the following line:

```bash
API_key: "########## REPLACE THIS STRING WITH YOUR WandB API HASH KEY ########"
```
Replace the string `"########## REPLACE THIS STRING WITH YOUR WandB API HASH KEY ########"` with your actual API key to enable WandB integration.

### Usage
For dataset preparation, please refer to [DATASET.md](datasets/DATASET.md). For training and inference instructions, see [GETTING_STARTED.md](GETTING_STARTED.md).

### Citing This Paper
If you find this work useful in your research, please consider citing it using the following BibTeX entry:

```BibTeX
@article{sikdar2024interweaving,
  title={Interweaving Insights: High-Order Feature Interaction for Fine-Grained Visual Recognition},
  author={Sikdar, Arindam and Liu, Yonghuai and Kedarisetty, Siddhardha and Zhao, Yitian and Ahmed, Amr and Behera, Ardhendu},
  journal={International Journal of Computer Vision},
  pages={1--25},
  year={2024},
  publisher={Springer}
}
```
