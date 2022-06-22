cmake_minimum_required(VERSION 3.10.2)
project(MFCompress C)

set(CMAKE_C_STANDARD 11)

set(CMAKE_C_FLAGS "-O2 -Wall -D_FILE_OFFSET_BITS=64")

set(SOURCE_DIR "src")

set(SOURCES
        ${SOURCE_DIR}/mem.c
        ${SOURCE_DIR}/fasta.c
        ${SOURCE_DIR}/fcm.c
        ${SOURCE_DIR}/io.c
        ${SOURCE_DIR}/bitio.c
        ${SOURCE_DIR}/arith.c
        ${SOURCE_DIR}/arith_aux.c
        )
set(HEADERS
        ${SOURCE_DIR}/mem.h
        ${SOURCE_DIR}/fasta.h
        ${SOURCE_DIR}/fcm.h
        ${SOURCE_DIR}/io.h
        ${SOURCE_DIR}/bitio.h
        ${SOURCE_DIR}/arith.h
        ${SOURCE_DIR}/arith_aux.h
        ${SOURCE_DIR}/defs.h
        )

set(SOURCES_C
        ${SOURCES}
        ${SOURCE_DIR}/MFCompressC.c
        )

set(SOURCES_D
        ${SOURCES}
        ${SOURCE_DIR}/MFCompressD.c
        )
add_executable(MFCompressC
        ${SOURCES_C} ${HEADERS}
        )

add_executable(MFCompressD
        ${SOURCES_D} ${HEADERS}
        )


target_link_libraries(MFCompressC m)
target_link_libraries(MFCompressD m)