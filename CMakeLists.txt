cmake_minimum_required(VERSION 2.8.3)

project(cal_pnp)


# set compilation
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)
add_definitions(-Wall -Wextra -Wno-unused-parameter -g)

# find libraries
find_package(OpenCV)

# common include directories
include_directories(
    ${PROJECT_SOURCE_DIR}/src
    ${OpenCV_INCLUDE_DIRS}
)

# find all source files
file(GLOB_RECURSE
    src_files
    ${PROJECT_SOURCE_DIR}/src/*.cpp
    )

# common library
add_executable(
    ${PROJECT_NAME}
    ${src_files}
)
target_link_libraries(
    ${PROJECT_NAME}
    ${OpenCV_LIBS}
)