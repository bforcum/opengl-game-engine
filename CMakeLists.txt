cmake_minimum_required(VERSION 3.12.0)

if (POLICY CMP0141)
    cmake_policy(SET CMP0141 NEW)
    set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project(game-engine VERSION 0.1.0 LANGUAGES C CXX)

find_package(SDL3 CONFIG REQUIRED)
set(SDL_TEST off)
set(BUILD_SHARED_LIBS off)

add_executable(${PROJECT_NAME}
	src/config.hpp
	src/main.cpp
)

target_link_libraries(${PROJECT_NAME} PRIVATE SDL3::SDL3)