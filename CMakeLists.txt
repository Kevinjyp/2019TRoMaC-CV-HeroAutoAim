cmake_minimum_required(VERSION 2.8)
PROJECT(main)
find_package(OpenCV 3.4.3)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c++11 -march=native")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -march=native")
include_directories(${OpenCV_INCLUDE_DIRS})
ADD_EXECUTABLE(main ./main/main.cpp
./camera/camera.cpp
./camera/camera.h
./detector/ArmorDetector.cpp
./detector/ArmorDetector.h
./main/ThreadControl.cpp
./main/ThreadControl.h
./fusion/CoordinatesFusion.cpp
./fusion/CoordinatesFusion.h
./uart/serial.cpp
./uart/serial.hpp
./tools/MathTools.cpp
./tools/MathTools.h
./predictor/Predictor.cpp
./predictor/Predictor.h
./predictor/KalmanFilter.cpp
./predictor/KalmanFilter.h
./decision/Decision.cpp
./decision/Decision.h
        )
target_link_libraries(main ${OpenCV_LIBS})
find_package(Threads)
target_link_libraries(main ${CMAKE_THREAD_LIBS_INIT})
find_package(X11 REQUIRED)
include_directories(${X11_INLUCDE_DIR})
target_link_libraries(main ${X11_LIBRARIES})