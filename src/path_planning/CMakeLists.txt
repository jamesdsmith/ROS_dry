cmake_minimum_required(VERSION 2.8.3)
project(path_planning)
find_package(catkin REQUIRED)
catkin_package()

include(ExternalProject)

externalproject_add(path_planning
  GIT_REPOSITORY https://github.com/jamesdsmith/path_planning
  GIT_TAG master
  CMAKE_ARGS -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX} -DSHARED_LIBS=ON
  UPDATE_COMMAND ""
)

install(FILES package.xml DESTINATION share/${PROJECT_NAME})
