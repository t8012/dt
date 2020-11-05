cmake_minimum_required (VERSION 2.8.11)

project (dt)

include_directories(src)

add_library(dt src/dt.c src/pmgr.c)

add_executable(dt-bin src/dt.c)
target_compile_definitions(dt-bin PUBLIC DT_MAIN)
set_target_properties(dt-bin PROPERTIES OUTPUT_NAME dt)

add_executable(pmgr src/pmgr.c src/dt.c)