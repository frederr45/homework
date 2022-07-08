cmake_minimum_required(VERSION 3.8)

project(hello CXX)

add_executable(hello hello_world.cpp example.cpp move_me_out.cpp)
target_compile_features(hello PUBLIC cxx_std_17)
if(MVSC)
    target_compile_options(hello PUBLIC /W4 /WX)
else()
    target_compile_options(hello PUBLIC -Wall -Wextra -Werror -pedantic -target arm64-apple-darwin21.3.0)
endif()