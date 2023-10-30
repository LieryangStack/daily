cmake_minimum_required(VERSION 3.10)

project(SerialPortTest VERSION 1.0)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)


add_executable(main main.cpp WzSerialPort.cpp)

# TODO 9: Use target_include_directories to include ${PROJECT_BINARY_DIR}
target_include_directories(main PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )