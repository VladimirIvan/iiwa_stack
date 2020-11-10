cmake_minimum_required(VERSION 3.5)
project(iiwa_description)

find_package(catkin REQUIRED COMPONENTS
  xacro
)

catkin_package()

file(GLOB xacro_files urdf/*.urdf.xacro)
xacro_add_files(${xacro_files} TARGET urdf INSTALL)

install(DIRECTORY models urdf www
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(DIRECTORY meshes DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
install(DIRECTORY urdf   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
install(DIRECTORY launch DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

