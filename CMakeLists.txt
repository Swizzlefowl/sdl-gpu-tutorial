# CMakeList.txt : CMake project for sdl-gpu-tutorial, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.25)

# Enable Hot Reload for MSVC compilers if supported.

project ("sdl-gpu-tutorial")
set(CMAKE_CXX_STANDARD 20)

include(FetchContent)
FetchContent_Declare(
        SDL3
        GIT_REPOSITORY https://github.com/libsdl-org/SDL.git
       # This will be a tag once SDL3 is released
        GIT_TAG origin/main
  )
FetchContent_MakeAvailable(SDL3)

FetchContent_Declare(
        fmtlib
        GIT_REPOSITORY https://github.com/fmtlib/fmt.git
       # This will be a tag once SDL3 is released
        GIT_TAG origin/master
  )
FetchContent_MakeAvailable(fmtlib)

# Add source to this project's executable.
add_executable (sdl-gpu-tutorial "sdl-gpu-tutorial.cpp" "sdl-gpu-tutorial.h")
target_link_libraries(sdl-gpu-tutorial PRIVATE fmt::fmt)
target_link_libraries(sdl-gpu-tutorial PRIVATE  SDL3::SDL3)

# TODO: Add tests and install targets if needed.
