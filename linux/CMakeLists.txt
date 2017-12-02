cmake_minimum_required(VERSION 3.5)   # CMake version check
project(CommandLineFPS)               # Create project "CommandLineFPS"
set(CMAKE_CXX_STANDARD 11)            # Enable c++11 standard

# Include our FindNcursesw.cmake file
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_MODULE_PATH})

# Find Ncursesw
find_package( Ncursesw REQUIRED )
include_directories( ${CURSES_INCLUDE_DIRS} )

# Add CommandLineFPS.cpp file of project root directory as source file
set(SOURCE_FILES CommandLineFPS.cpp)

# Add executable target with source files listed in SOURCE_FILES variable
add_executable(CommandLineFPS ${SOURCE_FILES})

# Link ncursesw library
target_link_libraries( CommandLineFPS ${CURSES_LIBRARIES} )
