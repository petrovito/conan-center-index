cmake_minimum_required(VERSION 3.8)

project(test_package CXX)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(daw-header-libraries REQUIRED CONFIG)

add_executable(${PROJECT_NAME} ../test_package/test_package.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE daw::daw-header-libraries)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_17)
