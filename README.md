# Open3D Demo

## 0. Dependencies
- Ubuntu 20.04
- CUDA 11.0
- Python 3.8
- Conda (recommended)

## 1. Install requirements.txt
```bash
# Conda environment
~/open3d-demo$ conda create -n o3d python=3.8 -y
(o3d) ~/open3d-demo$ conda activate o3d
(o3d) ~/open3d-demo/thirdparty/Open3D$ util/install_deps_ubuntu.sh
(o3d) ~/open3d-demo/thirdparty/Open3D$ conda install cmake
(o3d) ~/open3d-demo/thirdparty/Open3D$ pip install torch==1.8.1+cu111 torchvision==0.9.1+cu111 torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html
(o3d) ~/open3d-demo/thirdparty/Open3D$ mkdir build
(o3d) ~/open3d-demo/thirdparty/Open3D$ cd build
(o3d) ~/open3d-demo/thirdparty/Open3D/build$ cmake -DPython3_ROOT=$(which python) -DBUILD_PYTHON_MODULE=ON -DGLIBCXX_USE_CXX11_ABI=OFF -DBUILD_CUDA_MODULE=ON -DBUILD_PYTORCH_OPS=ON -DBUNDLE_OPEN3D_ML=ON -DOPEN3D_ML_ROOT=https://github.com/isl-org/Open3D-ML.git ..
(o3d) ~/open3d-demo/thirdparty/Open3D/build$ make -j install-pip-package

# Install Python packages
pip install -r requirements.txt
```
