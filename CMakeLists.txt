cmake_minimum_required(VERSION 3.15)
project(engine)

if (WIN32)
    set(CMAKE_PREFIX_PATH "D:\\Software Engineering\\SFML-2.6.1\\lib\\cmake\\SFML")
endif (WIN32)

find_package(SFML 2.5 COMPONENTS graphics audio system REQUIRED)

set(SOURCES "src/main.cpp"
            "src/components/engine.cpp"
            "src/components/window.cpp"
            "src/components/workingDirectory.cpp"
            "src/components/sphere.cpp")

set(INCLUDES "include/engine.hpp"
             "include/window.hpp"
             "include/workingDirectory.hpp"
             "include/sphere.hpp")

add_executable(engine ${SOURCES} ${INCLUDES})

target_link_libraries(engine sfml-graphics sfml-audio sfml-system)