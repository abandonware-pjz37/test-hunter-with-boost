cmake_minimum_required(VERSION 3.0)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.19.67.tar.gz"
    SHA1 "cd5ee033ae3949400781a3cf1bd79b79fba24f94"
)

project(TestBoost)

add_executable(foo foo.cpp)

hunter_add_package(Boost)
find_package(Boost CONFIG REQUIRED)
target_link_libraries(foo PUBLIC Boost::boost)
