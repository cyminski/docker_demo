FROM cyminski/armhf-ros-kinetic-ros-core

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y git vim
RUN apt-get install -y mpg123

# pull, build and source environment
RUN /bin/bash -c \
'git clone https://github.com/cyminski/demo.git && \
git clone https://github.com/Slamtec/rplidar_ros.git demo/src/rplidar_ros && \
cd demo && \
source /opt/ros/kinetic/setup.bash && \
catkin_make'

RUN echo "source /demo/devel/setup.bash"                             >> ~/.bashrc
RUN echo "alias run_listener=\"rosrun beginner_tutorials listener\"" >> ~/.bash_aliases
RUN echo "alias run_talker=\"rosrun beginner_tutorials talker\""     >> ~/.bash_aliases
RUN echo "alias run_lidar=\"roslaunch rplidar_ros rplidar.launch\""  >> ~/.bash_aliases
