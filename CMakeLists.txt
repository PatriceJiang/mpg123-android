cmake_minimum_required(VERSION 3.6)

#set(CMAKE_C_COMPILER clang)

project(mpg_123 C)

set(SOURCE_FILES 
    equalizer.c
    index.c
    layer2.c
    synth.c
    dct64.c
    format.c
    layer3.c
    ntom.c
    parse.c
    readers.c
    frame.c
    layer1.c
    libmpg123.c
    optimize.c
    synth_arm.S
    tabinit.c
    id3.c)


add_library(mpg123 STATIC ${SOURCE_FILES})

target_compile_options(mpg123 PRIVATE "-Wno-everything")

install(FILES mpg123.h DESTINATION include)
install(TARGETS mpg123 DESTINATION lib)