cmake_minimum_required (VERSION 2.8.11)

project (dt)

include_directories(PUBLIC include)

add_library(dt src/dt.c src/pmgr.c)
set_target_properties(dt PROPERTIES PUBLIC_HEADER "include/dt.h")
install(FILES include/dt.h DESTINATION include/dt)
install(TARGETS dt DESTINATION lib)


add_executable(dt-bin src/dt.c)
target_compile_definitions(dt-bin PUBLIC DT_MAIN)
set_target_properties(dt-bin PROPERTIES OUTPUT_NAME dt)
install(TARGETS dt-bin DESTINATION bin)

add_executable(pmgr src/pmgr.c src/dt.c)
install(TARGETS pmgr DESTINATION bin)