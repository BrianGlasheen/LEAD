cmake_minimum_required(VERSION 3.15)

project(LEAD)

file(GLOB_RECURSE CPP_SOURCE_FILES "src/*.h" "src/*.cpp")

# set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(
    ${PROJECT_NAME}
    ${CPP_SOURCE_FILES}
)

# target_compile_definitions(${PROJECT_NAME} PRIVATE GLFW_INCLUDE_NONE GLM_FORCE_XYZW_ONLY GLM_FORCE_QUAT_DATA_XYZW GLM_FORCE_QUAT_CTOR_XYZW)

add_subdirectory(external/GameNetworkingSockets)

target_link_libraries(${PROJECT_NAME} 
    PRIVATE
        GameNetworkingSockets
)
