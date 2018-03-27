cmake_minimum_required(VERSION 3.4.0)
project(GZipCodec CXX)

find_package(ZLIB REQUIRED)

add_library(gzipcodec GZipCodec/GZipCodec/GZipCodec.cpp GZipCodec/GZipCodec/GZipCodec.h)
target_include_directories(gzipcodec PRIVATE ${ZLIB_INCLUDE_DIRS})
target_link_libraries(gzipcodec ${ZLIB_LIBRARIES})

install(TARGETS gzipcodec DESTINATION lib)
install(FILES GZipCodec/GZipCodec/GZipCodec.h DESTINATION include)
