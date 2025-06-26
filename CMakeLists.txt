cmake_minimum_required(VERSION 3.21)

# C++ standard version.
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(ImGuiColorTextEdit STATIC
    TextEditor.cpp
    TextEditor.h
    LanguageDefinitions.cpp
)

target_include_directories(ImGuiColorTextEdit PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# 1-line dependency resolution

find_package(boost_regex CONFIG REQUIRED)
find_package(imgui CONFIG REQUIRED)

# Link
target_link_libraries(ImGuiColorTextEdit 
    PUBLIC 
        boost_regex 
        imgui::imgui
)
