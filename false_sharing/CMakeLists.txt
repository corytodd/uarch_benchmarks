set(EXE_TARGET_NAME false_sharing)

set(${EXE_TARGET_NAME}_ALIGNED_TYPE_SRC
        aligned_type.cpp
        )
set(${EXE_TARGET_NAME}_ATOMIC_INT_SRC
        atomic_int.cpp
        )
set(${EXE_TARGET_NAME}_FALSE_SHARING_SRC
        false_sharing.cpp
        )
set(${EXE_TARGET_NAME}_VARY_THREAD_SRC
        vary_thread.cpp
        )

add_executable(${EXE_TARGET_NAME}.aligned_types ${${EXE_TARGET_NAME}_ALIGNED_TYPE_SRC})
add_executable(${EXE_TARGET_NAME}.atomic_ints ${${EXE_TARGET_NAME}_ATOMIC_INT_SRC})
add_executable(${EXE_TARGET_NAME}.false_sharing ${${EXE_TARGET_NAME}_FALSE_SHARING_SRC})
add_executable(${EXE_TARGET_NAME}.vary_thread ${${EXE_TARGET_NAME}_VARY_THREAD_SRC})

find_package(benchmark CONFIG REQUIRED)

target_link_libraries(${EXE_TARGET_NAME}.aligned_types PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )
target_link_libraries(${EXE_TARGET_NAME}.atomic_ints PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )
target_link_libraries(${EXE_TARGET_NAME}.false_sharing PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )
target_link_libraries(${EXE_TARGET_NAME}.vary_thread PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )

install(TARGETS ${EXE_TARGET_NAME}.aligned_types DESTINATION bin)
install(TARGETS ${EXE_TARGET_NAME}.atomic_ints DESTINATION bin)
install(TARGETS ${EXE_TARGET_NAME}.false_sharing DESTINATION bin)
install(TARGETS ${EXE_TARGET_NAME}.vary_thread DESTINATION bin)


