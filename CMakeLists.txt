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
set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH} ${PROJECT_SOURCE_DIR}/deps")
# find_package(cppnetlib 0.11.0 REQUIRED)

set(Uri_BUILD_TESTS no)
add_subdirectory(deps/cpp-netlib)
include_directories(${CPPNETLIB_INCLUDE_DIRS})
target_link_libraries(${SERVER_TARGET_EXEC} ${CPPNETLIB_LIBRARIES})

