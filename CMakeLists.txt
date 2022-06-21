cmake_minimum_required(VERSION 3.10.2)
project(MFCompress C)

set(CMAKE_C_STANDARD 11)

set(CMAKE_C_FLAGS "-O2 -Wall -D_FILE_OFFSET_BITS=64")

add_executable(MFCompressC
        MFCompressC.c
        mem.c mem.h
        fasta.c fasta.h
        fcm.c fcm.h
        io.c io.h
        bitio.c bitio.h
        arith.c arith.h
        arith_aux.c arith_aux.h
        defs.h
        )

add_executable(MFCompressD
        MFCompressD.c
        mem.c mem.h
        fasta.c fasta.h
        fcm.c fcm.h
        io.c io.h
        bitio.c bitio.h
        arith.c arith.h
        arith_aux.c arith_aux.h
        defs.h
        )


target_link_libraries(MFCompressC m)
target_link_libraries(MFCompressD m)