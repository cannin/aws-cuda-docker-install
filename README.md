# From: https://medium.com/google-cloud/jupyter-tensorflow-nvidia-gpu-docker-google-compute-engine-4a146f085f17

# Install CUDA
sudo bash install-cuda.sh

# Install Docker
sudo bash install-docker.sh

# Install Nvidia-Docker
wget https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.1/nvidia-docker_1.0.1-1_amd64.deb
sudo dpkg -i nvidia-docker*.deb

# Start Nvidia-Docker
sudo nvidia-docker-plugin &

# Check GPU found
sudo nvidia-docker run --rm nvidia/cuda nvidia-smi

# Simple Tensorflow Test
sudo nvidia-docker run --rm --name tf1 -p 8888:8888 -p 6006:6006 gcr.io/tensorflow/tensorflow:latest-gpu jupyter notebook --allow-root
