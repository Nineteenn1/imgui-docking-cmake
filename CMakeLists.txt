cmake_minimum_required(VERSION 3.10)
project(IMGUI)

set(IMGUI_ROOT ${CMAKE_CURRENT_SOURCE_DIR})


# Engine-specific backends here
option(IMGUI_BUILD_BACKENDS ON)

set(IMGUI_SOURCES imconfig.h imgui_demo.cpp imgui_draw.cpp 
imgui_internal.h imgui_tables.cpp imgui_widgets.cpp imgui.cpp 
imgui.h imstb_rectpack.h imstb_textedit.h imstb_truetype.h 
backends/imgui_impl_opengl3.cpp backends/imgui_impl_opengl3.h 
backends/imgui_impl_glfw.h backends/imgui_impl_glfw.cpp)


# if(IMGUI_BUILD_BACKENDS)
#     list(APPEND IMGUI_SOURCES  )
# endif(IMGUI_BUILD_BACKENDS)


add_library(${PROJECT_NAME} STATIC ${IMGUI_SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC ${IMGUI_ROOT})
target_include_directories(${PROJECT_NAME} PUBLIC ../glad/include/)
target_include_directories(${PROJECT_NAME} PUBLIC ../glfw/include/)