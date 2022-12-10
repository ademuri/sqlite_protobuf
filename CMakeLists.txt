cmake_minimum_required(VERSION 3.2)

# Search for modules in the cmake/ directory
set(CMAKE_MODULE_PATH
    ${CMAKE_MODULE_PATH}
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake"
)

option(sqlite_protobuf_BUILD_TESTS "Build tests" ON)

add_subdirectory(src)
add_subdirectory(example)

if (sqlite_protobuf_BUILD_TESTS)
    enable_testing()
    add_subdirectory(tests)
endif (sqlite_protobuf_BUILD_TESTS)
