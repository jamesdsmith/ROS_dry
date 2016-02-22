cmake_minimum_required(VERSION 2.8.3)
project(ceres)
find_package(catkin REQUIRED)
catkin_package()

include(ExternalProject)

externalproject_add(ceres
  GIT_REPOSITORY https://ceres-solver.googlesource.com/ceres-solver
  GIT_TAG 1.11.0
  CMAKE_ARGS -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX} -DSHARED_LIBS=ON
  UPDATE_COMMAND ""
)

install(FILES package.xml DESTINATION share/${PROJECT_NAME})
