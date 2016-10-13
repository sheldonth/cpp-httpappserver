cmake_minimum_required(VERSION 3.2.2)
project(at-zeromq)
set(HEADERS
  ${PROJECT_SOURCE_DIR}/server.h
)
set(OBJECTS
  ${PROJECT_SOURCE_DIR}/server.cpp
  ${PROJECT_SOURCE_DIR}/main.cpp
)


