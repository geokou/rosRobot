<?xml version="1.0"?>
    <robot name="koutsoudakisbot">
      <link name="base_link">
        <visual name="mainbody">
<origin xyz="0 0 0" rpy="0 0 0" />
          <geometry>
            <cylinder length="0.6" radius="0.2"/>
          </geometry>
        </visual>
<!-- Base collision, mass and inertia -->
    <collision>
      <origin xyz="0 0 0" rpy="0 0 0" />
      <geometry>
                <cylinder length="0.7" radius="0.22"/>
      </geometry>
    </collision>
    <inertial>
    <mass value="10"/>
    <inertia ixx="0.4" ixy="0.0" ixz="0.0" iyy="0.4" iyz="0.0" izz="0.2"/>
     </inertial>
  <!-- Caster -->
    <visual name="caster">
      <origin xyz="0 0.15 -0.29" rpy="0 0 0" />
      <geometry>
        <sphere radius="0.05" />
      </geometry>
    </visual>
<!-- Caster collision, mass and inertia -->
    <collision>
      <origin xyz="0 0.15 -0.29" rpy="0 0 0" />
      <geometry>
          <sphere radius="0.06" />
      </geometry>
    </collision>
    <inertial>
      <mass value="1"/>
      <inertia ixx="0.0001" ixy="0.0" ixz="0.0" iyy="0.0001" iyz="0.0" izz="0.0001"/>
    </inertial>
      </link>
   
     <link name="right_leg">
       <visual>

         <geometry>
           <box size="0.6 0.1 0.2"/>
         </geometry>
<material name="blue">
        <color rgba="0 0.5 1 1"/>
      </material>
       </visual>
     </link>
   
     <joint name="base_to_right_leg" type="fixed">
       <parent link="base_link"/>
       <child link="right_leg"/>
     </joint>
   
  <!-- Right Wheel -->
  <link name="right_wheel">
    <visual>
      <origin xyz="0 0 0" rpy="1.570795 0 1.570795" />
      <geometry>
          <cylinder length="0.1" radius="0.35" />
      </geometry>
  <material name="black">
       <cylinder length="0.1" radius="0.35" />
      </material>
    </visual>
 <!--Right Wheel , mass and inertia -->
  <collision>
    <geometry>
      <cylinder length="0.15" radius="0.355" />
    </geometry>
   </collision>
    <inertial>
      <mass value="0.8"/>
<inertia ixx="0.01" ixy="0.0" ixz="0.0" iyy="0.005" iyz="0.0" izz="0.005"/>
    </inertial>
  </link>
  <joint name="joint_right_wheel" type="continuous">
    <parent link="base_link"/>
    <child link="right_wheel"/>
    <origin xyz="-0.30 0 0" rpy="0 0 0" /> 
    <axis xyz="1 0 0" />
  </joint>

  <!-- Left Wheel -->
  <link name="left_wheel">
    <visual>
      <origin xyz="0 0 0" rpy="1.570795 0 1.570795" />
      <geometry>
          <cylinder length="0.1" radius="0.35" />
      </geometry>
  <material name="black">
        <color rgba="0.05 0.05 0.05 1"/>
      </material>
    </visual>
 <!--Right Wheel , mass and inertia -->
  <collision>
    <geometry>
      <cylinder length="0.15" radius="0.355" />
    </geometry>
   </collision>
    <inertial>
      <mass value="0.8"/>
<inertia ixx="0.01" ixy="0.0" ixz="0.0" iyy="0.005" iyz="0.0" izz="0.005"/>
    </inertial>
  </link>
  <joint name="joint_left_wheel" type="continuous">
    <parent link="base_link"/>
    <child link="left_wheel"/>
    <origin xyz="0.30 0 0" rpy="0 0 0" /> 
    <axis xyz="1 0 0" />
  </joint>
<!-- Head -->
   <link name="head">
      <visual>
        <geometry>
         <sphere radius="0.2"/>
        </geometry>
        <material name="white">
       <color rgba="1 1 1 1"/>
     </material>
      </visual>
 <!--Head collision, mass and inertia -->
  <collision>
    <geometry>
       <sphere radius="0.22" />
    </geometry>
   </collision>
    <inertial>
      <mass value="0.8"/>
      <inertia ixx="0.0001" ixy="0.0" ixz="0.0" iyy="0.0001" iyz="0.0" izz="0.0001"/>
    </inertial>
    </link>
<joint name="head_camera" type="continuous">
      <parent link="base_link"/>
      <child link="head"/>
      <origin xyz="0 0 0.3"/>
<axis xyz="0 0 1" />
    </joint>

<link name="box">
    <visual>
      <geometry>
         <box size="0.08 0.08 0.08"/>
      </geometry>
      <material name="blue"/>
    </visual>
 <!--box collision, mass and inertia -->
  <collision>
    <geometry>
     <box size="0.09 0.09 0.09"/>
    </geometry>
   </collision>
    <inertial>
      <mass value="0.2"/>
      <inertia ixx="0.0001" ixy="0.0" ixz="0.0" iyy="0.0001" iyz="0.0" izz="0.0001"/>
    </inertial>
   </link>
<joint name="tobox" type="fixed">
     <parent link="head"/>
     <child link="box"/>
     <origin xyz="0 0.1 0.15"/>
   </joint>

<gazebo reference="base_link">
  <material>Gazebo/Red</material>
</gazebo>
<gazebo reference="head">
  <material>Gazebo/White </material>
</gazebo>
<gazebo reference="right_wheel">
  <material>Gazebo/Black</material>
</gazebo>
<gazebo reference="left_wheel">
  <material>Gazebo/Black</material>
</gazebo>

 
   
   </robot>
