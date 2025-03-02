cmake_minimum_required(VERSION 3.5)

project(09.homework)


set(SOURCE_FILE1 "${CMAKE_SOURCE_DIR}/file1.txt")
set(DESTINATION_FILE1 "${CMAKE_BINARY_DIR}/file1.txt") 

set(SOURCE_FILE2 "${CMAKE_SOURCE_DIR}/file2.txt")  
set(DESTINATION_FILE2 "${CMAKE_BINARY_DIR}/file2.txt")

configure_file(${SOURCE_FILE1} ${DESTINATION_FILE1} COPYONLY) 
configure_file(${SOURCE_FILE2} ${DESTINATION_FILE2} COPYONLY) 


add_custom_target(copy_files ALL DEPENDS ${DESTINATION_FILE1} ${DESTINATION_FILE2})

add_executable(topk_words-origin topk_words-origin.cpp)
set_target_properties(topk_words-origin PROPERTIES CXX_STANDARD 17 CXX_STANDARD_REQUIRED ON)


add_executable(topk_words-mode topk_words-mode.cpp)
set_target_properties(topk_words-mode  PROPERTIES CXX_STANDARD 17 CXX_STANDARD_REQUIRED ON)

