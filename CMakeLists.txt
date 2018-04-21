cmake_minimum_required (VERSION 3.1.3)
project (mini-cxx-http-example)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set (EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

set (CMAKE_CXX_STANDARD 11)
set (CMAKE_CXX_STANDARD_REQUIRED ON)

set (Boost_USE_STATIC_LIBS OFF)
set (Boost_USE_MULTITHREADED OFF)
set (Boost_USE_STATIC_RUNTIME OFF)

find_package (Boost REQUIRED COMPONENTS program_options system)
find_package (Threads REQUIRED)

include_directories (
  ${PROJECT_SOURCE_DIR}/third_party/json
  ${PROJECT_SOURCE_DIR}/third_party/websocketpp
  ${Boost_INCLUDE_DIR}
)

add_subdirectory (src)
