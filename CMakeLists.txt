CMAKE_MINIMUM_REQUIRED(VERSION 3.16)

SET(CMAKE_CXX_STANDARD 11)

project(image_convolution)

ADD_SUBDIRECTORY(./src ../bin/main)

ADD_SUBDIRECTORY(./tests ../bin/tests)

ADD_SUBDIRECTORY(googletest)

find_package(OpenMP)
if(OpenMP_CXX_FOUND)
    TARGET_LINK_LIBRARIES(manip_image PUBLIC OpenMP::OpenMP_CXX)
    TARGET_LINK_LIBRARIES(test PUBLIC OpenMP::OpenMP_CXX gtest)
endif()