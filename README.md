# 2wd-robot-in-gazebo-and-rviz

The my_robot package includes a 2 wheel drive robot with camera and laser scan in gazebo.

command velocities --> /cmd_vel 
Camera             --> /rgb/image_raw
laser scan         --> /scan

The topics can be changed in the my_robot/urdf/my_robot.gazebo file

roslaunch my_robot world.launch ---> launches the robot in an empty gazebo world and launches rviz.
 
Data visualisation in rviz:
            fixed frame        --> odom
        Use Add and select robot state to view the bot in rviz
                     select camera --> edit topic to /rgb/image_raw  --> to view images
                     select laser scan --> edit topic to /scan --> to view laser scan
                     
 To launch robot in a different world-
     1.place required .world file in my_robot/worlds directory
     2.edit the <arg name="world_file" default="$(find my_robot)/worlds/empty.world"/> 
                                              as                                      
                <arg name="world_file" default="$(find my_robot)/worlds/{name-of-your-world-file}.world"/> 
       in the my_robot/launch/world.launch file.
