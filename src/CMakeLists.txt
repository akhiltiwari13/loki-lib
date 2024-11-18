# Specify the library

# Set C++14 standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(LOKI_SOURCES
${CMAKE_CURRENT_SOURCE_DIR}/LevelMutex.cpp
${CMAKE_CURRENT_SOURCE_DIR}/OrderedStatic.cpp
${CMAKE_CURRENT_SOURCE_DIR}/SafeFormat.cpp
${CMAKE_CURRENT_SOURCE_DIR}/Singleton.cpp
${CMAKE_CURRENT_SOURCE_DIR}/SmallObj.cpp
${CMAKE_CURRENT_SOURCE_DIR}/SmartAssert.cpp
${CMAKE_CURRENT_SOURCE_DIR}/SmartPtr.cpp
${CMAKE_CURRENT_SOURCE_DIR}/StrongPtr.cpp
)

message(STATUS "LOKI_SOURCES: ${LOKI_SOURCES}")
add_library(loki STATIC ${LOKI_SOURCES})
# add_library(loki STATIC
# ${CMAKE_CURRENT_SOURCE_DIR}
# )
# add_executable(loki source1.cpp source2.cpp)
set_target_properties(loki PROPERTIES LINKER_LANGUAGE CXX)
# Include directories
target_include_directories(loki PUBLIC ${CMAKE_SOURCE_DIR}/include)
