cmake_minimum_required(VERSION 3.5)

project(BotWatcher  LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(lib/cdlpp/use.cmake)

cdlpp(lib/cdlpp)

add_executable(${PROJECT_NAME}
    ${CDLPP_SRC_FILES}
    src/main.cpp
)

target_include_directories(${PROJECT_NAME} PRIVATE
    ${CDLPP_INCLUDE_DIRS}
    include/
)

cdlpp_libs()

configure_file(config.json ./ COPYONLY)

