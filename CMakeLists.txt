cmake_minimum_required(VERSION 3.5)

project(01.hello_world)

add_executable(hello_world 
    hello_world.cpp
    example.cpp
    example.h
    move_me_out.cpp
    move_me_out.h
)

target_compile_features(hello_world PUBLIC cxx_std_17)
if (MSVC)
    target_compile_options(hello_world PUBLIC /W4 /WX)
else()
    target_compile_options(hello_world PUBLIC -Wall -Wextra -Werror -pedantic)
endif()

set_target_properties(hello_world PROPERTIES
    CXX_STANDARD 17
    CXX_STANDARD_REQUIRED ON
)