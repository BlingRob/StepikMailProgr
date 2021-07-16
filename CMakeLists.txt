# CMakeList.txt: проект CMake для StepikHttpServer; включите исходный код и определения,
# укажите здесь логику для конкретного проекта.
#
cmake_minimum_required (VERSION 2.8)

project("StepikHttpServer")
set(CMAKE_CXX_STANDARD 11)
//set (BOOST_ROOT "C:/boost_1_76_0/")
//set(Boost_INCLUDE_DIR "C:/boost_1_76_0/")
//set(Boost_LIBRARY_DIR "C:/boost_1_76_0/stage/lib/")
find_package(Boost 1.76.0 REQUIRED)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
  link_directories(${Boost_LIBRARY_DIR})
  target_link_libraries (${PROJECT_NAME} ${Boost_LIBRARIES})
endif()

# Добавьте источник в исполняемый файл этого проекта.
add_executable (StepikHttpServer "StepikHttpServer.cpp" "Headers.h" "Parser.h" "Server.h" "Server.cpp")

# TODO: Добавьте тесты и целевые объекты, если это необходимо.
