cmake_minimum_required(VERSION 3.12.0)
project(game-engine VERSION 0.1.0 LANGUAGES C CXX)

include(FetchContent)
FetchContent_Declare(
	glfw
	GIT_REPOSITORY https://github.com/glfw/glfw.git
	GIT_TAG 7b6aead9fb88b3623e3b3725ebb42670cbe4c579
)

FetchContent_MakeAvailable(glfw)

find_package(OpenGL REQUIRED)

add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE ${GLFW_LIBRARY})

target_link_libraries(${PROJECT_NAME} glfw OpenGL::GL)
