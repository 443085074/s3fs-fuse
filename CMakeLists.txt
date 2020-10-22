IF(${CMAKE_MAJOR_VERSION} GREATER  2)
    cmake_minimum_required(VERSION 3.0.0)
    project(s3fs-fuse VERSION 0.1.0) #这种定义方式camke 2.8.0 不支持，要报错
ELSE()
    cmake_minimum_required(VERSION 2.8.0)
    project(s3fs-fuse)
    set(VERSION 0.1.0)
ENDIF()
#
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -Wall -g -ggdb")
set(CMAKE_C_FLAGS_DEBUG "-O0 -Wall -g -ggdb")
set(CMAKE_CXX_FLAGS_RELEASE  "-O0 -Wall -g")
set(CMAKE_C_FLAGS_RELEASE  "-O0 -Wall -g")

#设置相关输出到统一目录
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x -fPIC -Wno-unused-function")
#SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fPIC")
set(CMAKE_INSTALL_PREFIX "/opt/sobey/amfs")
set(CMAKE_INSTALL_RPATH "/opt/sobey/amfs/lib")
include_directories(/usr/local/include/)
link_directories(/usr/local/lib)

add_subdirectory(src)