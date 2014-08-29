cmake_minimum_required(VERSION 2.8.3)
project(ed_examples)

find_package(catkin REQUIRED COMPONENTS
    ed
)

# find_package(Boost REQUIRED COMPONENTS system program_options)
# find_package(PCL REQUIRED)
# find_package(OpenCV REQUIRED)

# ------------------------------------------------------------------------------------------------
#                                          CATKIN EXPORT
# ------------------------------------------------------------------------------------------------

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES bla
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

# ------------------------------------------------------------------------------------------------
#                                     ROS MESSAGES AND SERVICES
# ------------------------------------------------------------------------------------------------

# Generate messages
# add_message_files(
#    FILES
#    message1.msg
#    ...
# )

# Generate services
# add_service_files(
#    FILES
#    service1.srv
#    ...
# )

# Generate added messages and services with any dependencies listed here
# generate_messages(
#    DEPENDENCIES
#    geometry_msgs
#    ...
# )

# ------------------------------------------------------------------------------------------------
#                                              BUILD
# ------------------------------------------------------------------------------------------------

include_directories(
    include
    ${catkin_INCLUDE_DIRS}
)

# - - - - - - - - - - - - - - - - - - - - EXAMPLE: probe - - - - - - - - - - - - - - - - - - - - -

add_library(ed_example_probe
    src/probe_example/probe.cpp
)
target_link_libraries(ed_example_probe ${catkin_LIBRARIES})

add_executable(probe_example
    src/probe_example/probe_example.cpp
    #src/probe_example/probe.cpp
)
target_link_libraries(probe_example ${catkin_LIBRARIES})

