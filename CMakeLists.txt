# cmake_minimum_required(VERSION <specify CMake version here>)
cmake_minimum_required(VERSION 3.16)
project(  myqt  )

set(CMAKE_CXX_STANDARD 20)

# qt
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

# add directly in "CMAKE options" in settings
#set(Qt5_DIR $(brew --prefix qt5)/lib/cmake/qt5)
#set(Qt5_DIR /usr/local/opt/qt/lib/cmake/qt5)


if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

find_package(Qt5 COMPONENTS Widgets REQUIRED)

add_executable(myqt
        main.cpp
        )

target_link_libraries(myqt PUBLIC
        Qt5::Widgets)