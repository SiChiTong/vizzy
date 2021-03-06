cmake_minimum_required(VERSION 2.8.7)

# find YARP
find_package(YARP REQUIRED)

  SET(CMAKE_CXX_FLAGS_RELEASE "-Wall -O2 -finline-functions -fpredictive-commoning -fgcse-after-reload -ftree-slp-vectorize -ftree-loop-distribute-patterns -fipa-cp-clone -funswitch-loops -fvect-cost-model -ftree-partial-pre")
  SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS_RELEASE}") #Default build mode is release mode

# add YARP include directories
include_directories(${YARP_INCLUDE_DIRS})
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

# set up our program
add_executable(vizzy_right_arm vizzy_right_arm.cpp)
add_executable(vizzy_left_arm vizzy_left_arm.cpp)
add_executable(vizzy_head vizzy_head.cpp)
add_executable(vizzy_waist vizzy_waist.cpp)
add_executable(vizzy_head_manual vizzy_head_manual.cpp)
add_executable(vizzy_upper_body_manual vizzy_upper_body_manual.cpp)
add_executable(vizzyUpperBodyJoints vizzyUpperBodyJoints.cpp)
add_executable(vizzyUpperBodyJointsSim vizzyUpperBodyJointsSim.cpp)

# link with YARP libraries
target_link_libraries(vizzy_right_arm ${YARP_LIBRARIES})
target_link_libraries(vizzy_left_arm ${YARP_LIBRARIES})
target_link_libraries(vizzy_head ${YARP_LIBRARIES})
target_link_libraries(vizzy_waist ${YARP_LIBRARIES})
target_link_libraries(vizzy_head_manual ${YARP_LIBRARIES})
target_link_libraries(vizzy_upper_body_manual ${YARP_LIBRARIES})
target_link_libraries(vizzyUpperBodyJoints ${YARP_LIBRARIES})
target_link_libraries(vizzyUpperBodyJointsSim ${YARP_LIBRARIES})
