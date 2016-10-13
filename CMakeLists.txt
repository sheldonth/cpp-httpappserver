cmake_minimum_required(VERSION 3.2.2)
project(at-zeromq)
set(HEADERS
  ${PROJECT_SOURCE_DIR}/server.h
)
set(OBJECTS
  ${PROJECT_SOURCE_DIR}/server.cpp
  ${PROJECT_SOURCE_DIR}/main.cpp
)
set(SERVER_TARGET_EXEC AppServer)
add_executable(${SERVER_TARGET_EXEC}
  ${HEADERS}
  ${OBJECTS}
)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

