project("final")
cmake_minimum_required (VERSION 2.8)

set(CMAKE_CXX_STANDARD 11)
find_package(Boost 1.76.0 REQUIRED)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
  link_directories(${Boost_LIBRARY_DIR})
  target_link_libraries (${PROJECT_NAME} ${Boost_LIBRARIES})
endif()

add_executable (StepikHttpServer "StepikHttpServer.cpp" "Headers.h" "Parser.h" "Server.h" "Server.cpp")
