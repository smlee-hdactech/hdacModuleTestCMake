cmake_minimum_required(VERSION 3.5)

project(hdacModuleTestCMake)

INCLUDE(CheckCXXCompilerFlag)
CHECK_CXX_COMPILER_FLAG(-std=c++11 HAVE_STD11)
if (HAVE_STD11)
    set(CMAKE_CXX_FLAGS -std=c++11)
endif()

add_subdirectory(strcodec)
add_subdirectory(hashes)
add_subdirectory(rpccall)
add_subdirectory(bcstructs)
add_subdirectory(keys)
add_subdirectory(moduleTest)

