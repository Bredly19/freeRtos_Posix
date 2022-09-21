cmake_minimum_required(VERSION 3.18)
project(freeRtos_Posix C)

set(CMAKE_C_STANDARD 99)

find_package(Threads REQUIRED)

include_directories(FreeRtos/Include FreeRtos/Source/portable/GCC/POSIX .)
add_executable(${PROJECT_NAME} FreeRtos/Source/list.c FreeRtos/Source/queue.c FreeRtos/Source/tasks.c
        FreeRtos/Source/timers.c FreeRtos/Source/portable/GCC/POSIX/port.c FreeRtos/Source/portable/MemMang/heap_3.c
        main.c)
target_link_libraries(${PROJECT_NAME} Threads::Threads)
