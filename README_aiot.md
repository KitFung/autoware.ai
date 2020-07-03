1. Install the nvidia-docker
2. `bash run.sh`
3. 
```
mkdir -p autoware.ai/src
cd autoware.ai
vcs import src < autoware.ai.repos
rosdep update
rosdep install -y --from-paths src --ignore-src --rosdistro $ROS_DISTRO

# if no cuda, remove the AUTOWARE_COMPILE_WITH_CUDA=1
AUTOWARE_COMPILE_WITH_CUDA=1 colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release
```