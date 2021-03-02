cmake_minimum_required(VERSION 3.10)

# set the project name and version
project(Tutorial VERSION 1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

configure_file(block.h)

# add the MathFunctions library
if(dynamic_block)
  add_subdirectory(dynamic_block)
  list(APPEND EXTRA_LIBS dynamic_block)
endif()

# add the MathFunctions library
if(static_block)
  add_subdirectory(static_block)
  list(APPEND EXTRA_LIBS static_block)
endif()

target_include_directories(source
          INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
          )

