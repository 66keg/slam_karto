cmake_minimum_required(VERSION 3.1)
project(slam_karto)

find_package(catkin REQUIRED
  COMPONENTS
    cmake_modules
    message_filters
    nav_msgs
    open_karto
    rosconsole
    roscpp
    sensor_msgs
    sparse_bundle_adjustment
    tf
    visualization_msgs
    rosbag
)
find_package(Eigen REQUIRED)

include_directories(${catkin_INCLUDE_DIRS} ${EIGEN_INCLUDE_DIRS})
add_definitions(${EIGEN_DEFINITIONS})

catkin_package()

add_executable(slam_karto src/slam_karto.cpp src/spa_solver.cpp)
target_link_libraries(slam_karto ${catkin_LIBRARIES})

install(TARGETS slam_karto
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

add_executable(slam_karto_offline src/slam_karto_offline.cpp src/spa_solver.cpp)
target_link_libraries(slam_karto_offline ${catkin_LIBRARIES})
