cmake_minimum_required(VERSION 3.8.0)
project(stbimage)

add_library(stbimage SHARED stb_image.c stb_image.h)

target_include_directories(stbimage PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

set_target_properties(stbimage PROPERTIES PUBLIC_HEADER stb_image.h)

install(TARGETS stbimage
        EXPORT stbimage-targets
        RUNTIME DESTINATION bin
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib/static
        PUBLIC_HEADER DESTINATION include)
