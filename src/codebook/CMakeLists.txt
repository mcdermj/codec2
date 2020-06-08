cmake_minimum_required(VERSION 3.13)

message("Configuring Native Codebook from ${CMAKE_SOURCE_DIR} to ${CMAKE_BINARY_DIR}")
message("${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_BINARY_DIR}")
message("$ENV{PWD}")

add_executable(generate_codebook generate_codebook.c)
target_link_libraries(generate_codebook m)

message("Writing ${CMAKE_BINARY_DIR}/ImportExecutables.cmake")
export(TARGETS generate_codebook
        FILE ${CMAKE_BINARY_DIR}/ImportExecutables.cmake
        NAMESPACE native-)