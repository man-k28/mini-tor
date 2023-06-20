cmake_minimum_required(VERSION 3.5)

set(TARGET_NAME minitor)

file(GLOB_RECURSE HEADER_FILES "*.h")
file(GLOB_RECURSE SOURCE_FILES "*.cpp" "*.inl")

add_library(${TARGET_NAME} STATIC)

target_sources(${TARGET_NAME} PRIVATE ${HEADER_FILES} ${SOURCE_FILES})
target_include_directories(${TARGET_NAME} PUBLIC ../)
target_link_libraries(${TARGET_NAME}
    Crypt32
    Secur32
    Bcrypt
    Ws2_32)
