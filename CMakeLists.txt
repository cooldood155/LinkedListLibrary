cmake_minimum_required(VERSION 3.16)
project(LLlib VERSION 0.1.0 LANGUAGES C CXX)

# C library sources
set(C_SOURCES
    src/sll/building_list.c
)
# C++ library sources
set(CXX_SOURCES
    src/dll/building_list.cxx
)

# ---------------------------------------------------------
# Build STATIC libraries
# ---------------------------------------------------------
add_library(sll_static STATIC ${C_SOURCES})
add_library(dll_static STATIC ${CXX_SOURCES})

set_target_properties(sll_static PROPERTIES OUTPUT_NAME "sll")
set_target_properties(dll_static PROPERTIES OUTPUT_NAME "dll")


# ---------------------------------------------------------
# Build SHARED libraries
# ---------------------------------------------------------
add_library(sll_dynamic SHARED ${C_SOURCES})
add_library(dll_dynamic SHARED ${CXX_SOURCES})

set_target_properties(sll_dynamic PROPERTIES OUTPUT_NAME "sll")
set_target_properties(dll_dynamic PROPERTIES OUTPUT_NAME "dll")


# ---------------------------------------------------------
# TEST executable
# ---------------------------------------------------------
add_executable(test_lib src/main.cxx)
target_link_libraries(test_lib PRIVATE sll_static)



# ---------------------------------------------------------
#               FINAL PRODUCED LIBRARIES / TESTS
# ---------------------------------------------------------
#   ____________________________________________________________________
#  |  Language  |         Static            |          Shared           |
#  |------------|---------------------------|---------------------------|
#  |  C:        |   sll.a / sll.lib         |   sll.so / sll.dll        |
#  |============|===========================|===========================|
#  |  C++:      |   dll.a / dll.lib         |   dll.so / dll.dll        |
#  |============|===========================|===========================|
#  |  Test EXE  |   test_lib.exe            |                           |
#  |____________|___________________________|___________________________|