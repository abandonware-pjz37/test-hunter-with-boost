cmake_minimum_required(VERSION 3.0)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.19.68-boost-test.tar.gz"
    SHA1 "c7e3daa63651df7a3ccafc857594cfb51fce05e5"
)

project(TestBoost)

add_executable(foo foo.cpp)

hunter_add_package(Boost COMPONENTS system)
find_package(Boost CONFIG REQUIRED COMPONENTS system)
target_link_libraries(foo PUBLIC Boost::system)
