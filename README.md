# Open3D Demo

## 0. Dependencies
- Ubuntu 20.04
- CUDA 11.1
- Python 3.8
- Conda (recommended)

## 1. Install with pre-built Python wheels
```bash
# Conda environment
~/open3d-demo$ conda create -n o3d python=3.8 -y
~/open3d-demo$ conda activate o3d

# Install Python packages
(o3d) ~/open3d-demo$ pip install -r requirements-torch-cuda.txt
(o3d) ~/open3d-demo$ pip install -r requirements.txt
# For CPU with MacOS, use the commands below
(o3d) ~/open3d-demo$ conda install pytorch==1.8.1 torchvision==0.9.1 torchaudio==0.8.1 -c pytorch
(o3d) ~/open3d-demo$ pip install -r requirements-cpu.txt
```

## 1-2. Build from source
```bash
# Conda environment
~/open3d-demo$ conda create -n o3d python=3.8 -y
~/open3d-demo$ conda activate o3d

# Build from source
(o3d) ~/open3d-demo$ cd thirdparty/Open3D
(o3d) ~/open3d-demo/thirdparty/Open3D$ util/install_deps_ubuntu.sh
(o3d) ~/open3d-demo/thirdparty/Open3D$ conda install cmake
(o3d) ~/open3d-demo/thirdparty/Open3D$ pip install torch==1.8.1+cu111 torchvision==0.9.1+cu111 torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html
(o3d) ~/open3d-demo/thirdparty/Open3D$ mkdir build
(o3d) ~/open3d-demo/thirdparty/Open3D$ cd build
(o3d) ~/open3d-demo/thirdparty/Open3D/build$ cmake -DPython3_ROOT=$(which python) -DBUILD_PYTHON_MODULE=ON -DGLIBCXX_USE_CXX11_ABI=OFF -DBUILD_CUDA_MODULE=ON -DBUILD_PYTORCH_OPS=ON -DBUNDLE_OPEN3D_ML=ON -DOPEN3D_ML_ROOT=https://github.com/isl-org/Open3D-ML.git .. # does not work for Open3D-ML and don't know why
(o3d) ~/open3d-demo/thirdparty/Open3D/build$ make -j install-pip-package
```