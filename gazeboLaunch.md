<launch>
  <!-- We resume the logic in gazebo_ros package empty_world.launch, -->
  <!-- changing only the name of the world to be launched -->
  <include file="$(find gazebo_ros)/launch/empty_world.launch">
    <arg name="world_name" value="$(find ros_robotics)/worlds/ddrobot.world"/>
   
    <arg name="paused" default="false"/>
    <arg name="use_sim_time" default="true"/>
    <arg name="gui" default="true"/>
    <arg name="headless" default="false"/>
    <arg name="debug" default="false"/>

  </include>

  <!-- Spawn dd_robot into Gazebo -->
  <node name="spawn_urdf" pkg="gazebo_ros" type="spawn_model"
     args="-file $(find ros_robotics)/urdf/dd_robot7.urdf -urdf -model dd_robot" />
</launch>
