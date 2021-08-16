set(EXE_TARGET_NAME branch_prediction)

set(${EXE_TARGET_NAME}_CALLS_SRC
        vf_calls.cpp
        )
set(${EXE_TARGET_NAME}_SIZE_SRC
        vf_size.cpp
        )

add_executable(${EXE_TARGET_NAME}.vf_calls ${${EXE_TARGET_NAME}_CALLS_SRC})
add_executable(${EXE_TARGET_NAME}.vf_size ${${EXE_TARGET_NAME}_SIZE_SRC})

find_package(benchmark CONFIG REQUIRED)

target_link_libraries(${EXE_TARGET_NAME}.vf_calls PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )
target_link_libraries(${EXE_TARGET_NAME}.vf_size PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )

install(TARGETS ${EXE_TARGET_NAME}.vf_calls DESTINATION bin)
install(TARGETS ${EXE_TARGET_NAME}.vf_size DESTINATION bin)


