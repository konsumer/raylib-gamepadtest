cmake_minimum_required(VERSION 3.18)

project(raylib-gamepadtest
  VERSION 0.0.1
  LANGUAGES C
)

if(POLICY CMP0135)
  cmake_policy(SET CMP0135 NEW)
  set(CMAKE_POLICY_DEFAULT_CMP0135 NEW)
endif()

if(POLICY CMP0077)
  cmake_policy(SET CMP0077 NEW)
  set(CMAKE_POLICY_DEFAULT_CMP0077 NEW)
endif()

if(POLICY CMP0169)
  cmake_policy(SET CMP0169 NEW)
  set(CMAKE_POLICY_DEFAULT_CMP0169 NEW)
endif()

# enable colors for ninja
set(CMAKE_COLOR_DIAGNOSTICS ON)

include(FetchContent)

FetchContent_Declare(
    raylib
    URL https://github.com/raysan5/raylib/archive/refs/tags/5.5.zip
)
FetchContent_MakeAvailable(raylib)

add_executable(${PROJECT_NAME} core_input_gamepad.c)
TARGET_LINK_LIBRARIES(${PROJECT_NAME} raylib)

IF (EMSCRIPTEN)
  SET(CMAKE_EXECUTABLE_SUFFIX ".mjs")
  TARGET_LINK_OPTIONS(host PRIVATE -sASSERTIONS=1 -sASYNCIFY -sALLOW_MEMORY_GROWTH=1)  
ENDIF()