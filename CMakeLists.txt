cmake_minimum_required(VERSION 3.17)
project(hashmap_c C)

set(CMAKE_C_STANDARD 99)

include_directories(.)

add_library(hashmap_c
        STATIC hashmap.c
        hashmap.h)

install(TARGETS hashmap_c EXPORT hashmap_cTargets
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib
        RUNTIME DESTINATION lib
        INCLUDES destination include)

install(EXPORT hashmap_cTargets
        FILE hashmap_cTargets.cmake
        NAMESPACE hashmap_c
        DESTINATION lib/cmake/hashmap_c)

