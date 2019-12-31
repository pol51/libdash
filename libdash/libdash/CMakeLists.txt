cmake_minimum_required(VERSION 3.12)

find_package(LibXml2 REQUIRED)
find_package(ZLIB REQUIRED)
find_package(CURL REQUIRED)

include_directories(include )

file(GLOB_RECURSE libdash_source *.cpp)

add_library(dash SHARED ${libdash_source})
target_link_libraries(dash CURL::libcurl ZLIB::ZLIB LibXml2::LibXml2)
