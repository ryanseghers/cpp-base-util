cmake_minimum_required (VERSION 3.16)
project(CppBaseUtil LANGUAGES CXX VERSION 0.0.0)

if (NOT TARGET CppBaseUtilLib)
    add_subdirectory("src" CppBaseUtilLib)
endif()

if (NOT TARGET CppBaseUtilTests)
    add_subdirectory("tests" CppBaseUtilTests)
endif()

#
# CTest on top of googletest, with test discovery
# (took trial and error between here and the tests CMakeLists.txt to get VS to discover the tests)
#
include(GoogleTest)
enable_testing()
