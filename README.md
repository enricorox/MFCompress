# MFCompress
A (working) fork of MFCompress-1.01

For the original work see [here](https://bioinformatics.ua.pt/software/mfcompress/).

This sequence file compressor can achieve better performance than `xz`.

## How to compile
1. `cmake .`
2. `make`

## How to run
To compress a file run:
`./MFCompressC -v -3 -o example.mfc example.fa` 

To decompress a file run:
`./MFCompressD -v -o example.fa example.mfc`
