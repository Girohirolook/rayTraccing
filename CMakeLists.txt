cmake_minimum_required(VERSION 3.15)

project(MyProject LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_custom_target(render
    COMMAND my_app > ${CMAKE_BINARY_DIR}/image.ppm
    DEPENDS my_app
    WORKING_DIRECTORY ${CMAKE_BINARY_DIR}
    COMMENT "Rendering image.ppm"
)

add_executable(my_app main.cpp)