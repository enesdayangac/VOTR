project(STRUCK)

cmake_minimum_required(VERSION 2.6)

find_package(OpenCV REQUIRED)

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release CACHE STRING "Build type" FORCE)
endif()

set(EIGEN3_INCLUDE_DIRS "C:/Users/enes/Dst3rdParty_x64_vs11NoCuda/Eigen/include/eigen3")
INCLUDE_DIRECTORIES ( src/GraphUtils ${EIGEN3_INCLUDE_DIRS} ${OpenCV_INCLUDE_DIRS})

add_executable(STRUCK
    src/Config.cpp
    src/Features.cpp
    src/HaarFeature.cpp
    src/HaarFeatures.cpp
    src/HistogramFeatures.cpp
    src/ImageRep.cpp
    src/LaRank.cpp
    src/main.cpp
    src/MultiFeatures.cpp
    src/RawFeatures.cpp
    src/Sampler.cpp
    src/Tracker.cpp
    src/GraphUtils/GraphUtils.cpp
    )

target_link_libraries(STRUCK ${OpenCV_LIBS} ${EIGEN2_LIBRARIES})
