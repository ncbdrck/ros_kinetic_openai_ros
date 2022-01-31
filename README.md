This repo contains Dockerfiles that will start from the **Nvidia/CUDAGL** image and automatically install ROS kinetic and all the packages to perform OpenAI with ROS.

- **dockerfile_nvidia_ros_kinetic** contains a clean installation of CUDA with ROS kinetic
- **dockerfile_openai_ros_kinetic** contains nvidia_ros with openai_ros framework with Pytorch/Tensorflow
- **dockerfile_openai_ros_sim_kinetic** contains openai_ros with fecth and iri_wam simulation
- **dockerfile_openai_ros_sim_vnc_kinetic** contains openai_ros_ simulations with vnc support for visualization

To create the Docker Images, execute the following code. 

```
git clone https://github.com/ncbdrck/ros_kinetic_openai_ros.git
cd ros_kinetic_openai_ros/ 
docker build -f dockerfile_nvidia_ros_kinetic -t nvidia_ros_kinetic .
docker build -f dockerfile_openai_ros -t openai_ros .
docker build -f dockerfile_openai_ros_sim -t openai_ros_sim .
docker build -f dockerfile_openai_ros_sim_vnc -t openai_ros_sim_vnc .
```

To create a Docker Container

```
docker run --name my-openai-v1 -it -v ~/tmp:/mytmp -p 5910:5910 --gpus all openai_ros_sim_v1
```
