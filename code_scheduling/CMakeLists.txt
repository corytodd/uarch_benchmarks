set(EXE_TARGET_NAME code_scheduling)

set(${EXE_TARGET_NAME}_SRC
        fast_mod.cpp
        )

add_executable(${EXE_TARGET_NAME} ${${EXE_TARGET_NAME}_SRC})

find_package(benchmark CONFIG REQUIRED)

target_link_libraries(${EXE_TARGET_NAME} PRIVATE
        benchmark::benchmark benchmark::benchmark_main
        )

install(TARGETS ${EXE_TARGET_NAME} DESTINATION bin)
