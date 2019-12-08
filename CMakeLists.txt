cmake_minimum_required(VERSION 2.8)
PROJECT(main)
find_package(OpenCV 3.4.3)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c++11 -march=native")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -march=native")
include_directories(${OpenCV_INCLUDE_DIRS})
ADD_EXECUTABLE(main /home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/main/main.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/camera/camera.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/camera/camera.h
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/detector/ArmorDetector.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/detector/ArmorDetector.h
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/main/ThreadControl.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/main/ThreadControl.h
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/fusion/CoordinatesFusion.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/fusion/CoordinatesFusion.h
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/uart/serial.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/uart/serial.hpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/tools/MathTools.cpp
/home/kevinjyp/Github/2019TRoMaC-CV-HeroAutoAim/tools/MathTools.h)
target_link_libraries(main ${OpenCV_LIBS})
find_package(Threads)
target_link_libraries(main ${CMAKE_THREAD_LIBS_INIT})
find_package(X11 REQUIRED)
include_directories(${X11_INLUCDE_DIR})
target_link_libraries(main ${X11_LIBRARIES})