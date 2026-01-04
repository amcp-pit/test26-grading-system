cmake_minimum_required(VERSION 3.1)
project(tests CXX)

set(CMAKE_CXX_STANDARD 20)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fsanitize=address -fsanitize=undefined -Wall -Wextra -pedantic -Werror")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -fsanitize=address -fsanitize=undefined")

if (IS_DIRECTORY ${STUDENT_DIR})
    set(STUDENT_SOURCE_DIR "${STUDENT_DIR}")
    add_subdirectory(${STUDENT_SOURCE_DIR})
else()
    message(FATAL_ERROR "${STUDENT_DIR} is not directory")
endif()
