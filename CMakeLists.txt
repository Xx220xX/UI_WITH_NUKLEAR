cmake_minimum_required(VERSION 3.17)
project(UI C)

set(CMAKE_C_STANDARD 11)
set(Nuklear extern/include/nuklear/nuklear.h extern/include/nuklear/nuklear.c)

link_directories(extern/lib)
include_directories(
        extern/include
        extern/include/nuklear extern/include/nuklear/src extern/include/nuklear/example
)
link_libraries( -lglfw3 -lopengl32 -lm -lGLU32 -lGLEW32 -lmingw32 )

add_executable(UI main.c
        ${Nuklear}
        )
#add_custom_command(
#        TARGET UI POST_BUILD
#        COMMAND ${CMAKE_COMMAND} -E copy_directory
#        "${PROJECT_SOURCE_DIR}/extern/bin/"
#        $<TARGET_FILE_DIR:UI>
#)