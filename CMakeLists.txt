#cd build
#cmake ..
#cmake --build . --config Release

#[[ 
cd build
cmake -Bbuild/win64 -H. -G "Visual Studio 15 2017 Win64"
cmake -Bbuild/win32 -H. -G "Visual Studio 15 2017"
cmake -Bbuild/mac -H. -G "Xcode"

cmake --build build/win64 --config Release
]]

cmake_minimum_required(VERSION 3.10.0)
project(MyProject VERSION 1.0.0)

message(STATUS "CMAKE_GENERATOR: ${CMAKE_GENERATOR}")
message(STATUS "CMAKE_SYSTEM_NAME: ${CMAKE_SYSTEM_NAME}")
message(STATUS "CMAKE_BUILD_TYPE: ${CMAKE_BUILD_TYPE}")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/library)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/library)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/binary)

add_subdirectory(app)