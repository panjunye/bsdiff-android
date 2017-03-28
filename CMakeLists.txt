cmake_minimum_required(VERSION 3.5)

project(bsdiff)

# add_definitions(-D_W32)

include_directories(bzlib)

set(TARGET_bsdiff_NAME bsdiff)

set(TARGET_bspatch_NAME bspatch)

file(GLOB TARGET_bsdiff_FILES "bzlib/*.c" "bsdiff.c")

file(GLOB TARGET_bspatch_FILES "bzlib/*.c" "bspatch.c")

add_library( ${TARGET_bsdiff_NAME} SHARED ${TARGET_bsdiff_FILES} ${ZLIB_SOURCES})

add_library( ${TARGET_bspatch_NAME} SHARED ${TARGET_bspatch_FILES} ${ZLIB_SOURCES})

add_executable(bsdiffm ${TARGET_bsdiff_FILES} ${ZLIB_SOURCES})

add_executable(bspatchm ${TARGET_bspatch_FILES} ${ZLIB_SOURCES})




