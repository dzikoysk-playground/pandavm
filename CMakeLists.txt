cmake_minimum_required(VERSION 3.5)
project(PandaVM)

set(CMAKE_CXX_STANDARD 17)

if(EXISTS ${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup()
else()
    message(WARNING "The file conanbuildinfo.cmake doesn't exist, you have to run conan install first")
endif()

set(SOURCE_FILES src/main.c)
add_executable(PandaVM ${SOURCE_FILES})
target_link_libraries(PandaVM ${CONAN_LIBS})
