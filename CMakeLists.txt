cmake_minimum_required(VERSION 3.26)
project(ElectricShadows)

set(CMAKE_CXX_STANDARD 20)

add_executable(ElectricShadows main.cpp)
add_subdirectory(include/glm)
include_directories(/usr/local/include)
include_directories(include)

find_package(Vulkan REQUIRED)
target_include_directories(${PROJECT_NAME} PUBLIC ${Vulkan_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan)

find_package(glfw3 CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} glfw)