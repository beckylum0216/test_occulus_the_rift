cmake_minimum_required(VERSION 3.10)

project(test_occulus_the_rift)

set(CMAKE_CXX_STANDARD 14)
set(GTEST_INCLUDE_DIR ${CMAKE_CURRENT_LIST_DIR}/googletest/include )
set(GTEST_LIBRARY ${CMAKE_CURRENT_LIST_DIR}/googletest/googletest/msvc/2010/gtest/Win32-Debug)
set(GTEST_MAIN_LIBRARY ${CMAKE_CURRENT_LIST_DIR}/googletest/googletest/msvc/2010/gtest/Win32-Debug)
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_LIST_DIR}/googletest/googletest/cmake)

#pthread??
set(PTHREAD_INCLUDE_DIR ${CMAKE_CURRENT_LIST_DIR}/pthread4w)

# Prevent GoogleTest from overriding our compiler/linker options
# when building with Visual Studio
#set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)


find_package(GTest REQUIRED)
find_package(Threads REQUIRED)


include_directories(.)
include_directories(${GTEST_INCLUDE_DIR})
include_directories(${PTHREAD_INCLUDE_DIR})

#add_subdirectory(${googletest_SOURCE_DIR} ${googletest_BINARY_DIR})



add_executable(
				test_occulus_the_rift
				main.cpp
				sampleTest.cpp

)

target_link_libraries(test_occulus_the_rift ${GTEST_LIBRARY} ${GTEST_MAIN_LIBRARY})