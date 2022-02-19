# Basic CMake setup
cmake_minimum_required(VERSION 3.12)
file(WRITE ${CMAKE_BINARY_DIR}/CACHEDIR.TAG "Signature: 8a477f597d28d172789f06886806bc55")

# Include the pico SDK from git
include(pico-sdk/pico_sdk_init.cmake)

# Define project
project(FIXME C CXX)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 14)
add_compile_options(-Wall -Wextra)
# FIXME: add_compile_options(-Werror)

# Init SDK and define the executables
pico_sdk_init()
add_executable(
    FIXME
    src/main.c
)
target_link_libraries(FIXME pico_stdlib)

# Enable USB and build map/bin/hex file etc.
pico_enable_stdio_usb(FIXME 1)
pico_add_extra_outputs(FIXME)
