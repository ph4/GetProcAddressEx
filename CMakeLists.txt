cmake_minimum_required(VERSION 3.10)

project(GetProcAddressEx LANGUAGES CXX)

# Define the library
add_library(GetProcAddressEx STATIC
    src/GetProcAddressEx.cpp
)

# Set C++ standard
target_compile_features(GetProcAddressEx PUBLIC cxx_std_11)

# Include headers
target_include_directories(GetProcAddressEx PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

# Optional test/example executable
add_executable(GetProcAddressExTest src/Main.cpp)
target_link_libraries(GetProcAddressExTest PRIVATE GetProcAddressEx)

