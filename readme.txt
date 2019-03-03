
Building bin using local libs is easy, just using "-Lpath -llibname" in the makefile, then both build and run can find it.
such as when depend libasound.so, just using "-L/usr/lib/x86_64-linux-gnu/libasound.so -lasound", then OK. But using a cross-compiled libs need a little more to do, you need to explicitly list it's location both building and running.

1. armso dir used to output a libcal.so, gcc is arm-none-linux-gnueabi-gcc;

2. armc dir contain: main.c using the libcal.so, and when building this dir, put this lib in current dir(or other dir can be seen);

3. when running, copy the bin to board, copy the lib to the /lib under target board, then run OK.

test with: samsung 6410 board;

additional info:
"libc.so.6" and other depending libs should be in the board already.
