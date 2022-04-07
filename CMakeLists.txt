cmake_minimum_required(VERSION 3.16)

project(glad)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_CXX_STANDARD 17)

# 测试程序的路径
set(INCROOT ${CMAKE_CURRENT_SOURCE_DIR}/include)
set(SRCROOT ${CMAKE_CURRENT_SOURCE_DIR}/src)

include_directories(${INCROOT})

file(GLOB GLAD_FILES_HEADER "${INCROOT}/*.h" "${INCROOT}/*/*.h")
file(GLOB GLAD_FILES_SOURCE "${SRCROOT}/*.c")

message("glad file: ${GLAD_FILES_HEADER} ${GLAD_FILES_SOURCE}")

add_library(glad STATIC ${GLAD_FILES_HEADER} ${GLAD_FILES_SOURCE})
