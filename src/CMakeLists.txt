cmake_minimum_required(VERSION 3.7)
project(yskip)

find_package(pybind11 REQUIRED)  # or add_subdirectory(pybind11)

add_library(yskip MODULE yskip.cpp)
target_link_libraries(yskip PRIVATE pybind11::module)
set_target_properties(yskip PROPERTIES PREFIX "${PYTHON_MODULE_PREFIX}"
                                         SUFFIX "${PYTHON_MODULE_EXTENSION}")