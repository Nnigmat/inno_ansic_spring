enable_testing()

find_package(Check REQUIRED)
find_package(Threads REQUIRED)

include_directories(${CHECK_INCLUDE_DIRS})

include_directories(. ../src)

add_executable(test_pq test_pq.c ../src/priority_queue.c)
add_executable(test_stack test_stack.c ../src/stack.c)

target_link_libraries(test_pq ${CHECK_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(test_stack ${CHECK_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})

add_test(test_stack ${CMAKE_CURRENT_BINARY_DIR}/test_stack)