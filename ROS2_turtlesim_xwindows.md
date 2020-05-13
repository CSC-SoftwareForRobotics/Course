

2020_05_07_1314__
installing docker

file needs to be called Dockerfile

On OSX, run xquartz and use the security setting to allow other processes to connect to xquartz:

	xquartz



install docker.

This command downloads ROS2 binaries
		
	docker pull osrf/ros:eloquent-desktop

This runs the docker image.

	docker run -it osrf/ros:eloquent-desktop

Now that your docker container is running, test that the `ros2` command is active.

	root@<container-id>:/# ros2 --help


*Can we run a graphical version of TurtleSim from here?*


in osx

	xhost + 127.0.0.1
	
in docker container

	export DISPLAY=host.docker.internal:0

Run turtlesim

	ros2 run turtlesim turtlesim_node &
	
run keyboard teleoperation

	ros2 run turtlesim turtle_teleop_key
	
	
Run a visualization tool to show the ros graph

	rqt_graph &
	
list the current topics

	ros2 topic list
	
start a new terminal and find the list of running docker images
	
	docker ps
	
Start another terminal connected to the same docker image:

	docker exec -it 061fda779ef1 bash
	
source the bash to set it up

	. /ros_entrypoint.sh
	
	
