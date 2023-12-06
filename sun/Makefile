all: webp webpdecoder sharpyuv

webp: libwebp.wasm
	../build/_deps/mod_wasm2c-src/bin/wasm2c libwebp.wasm -o libwebp.wasm.c
	gcc -c ../build/_deps/mod_wasm2c-src/wasm2c/wasm-rt-impl.c ../src/wasm2c_rt_minwasi.c ../src/wasm2c_rt_mem.c -I../build/_deps/rlbox-src/code/include -I../include -I../build/_deps/mod_wasm2c-src/wasm2c libwebp.wasm.c
	ar r libwebp.a libwebp.wasm.o wasm2c_rt_mem.o wasm2c_rt_minwasi.o wasm-rt-impl.o

webpdecoder: libwebpdecoder.wasm
	../build/_deps/mod_wasm2c-src/bin/wasm2c libwebpdecoder.wasm -o libwebpdecoder.wasm.c
	gcc -c ../build/_deps/mod_wasm2c-src/wasm2c/wasm-rt-impl.c ../src/wasm2c_rt_minwasi.c ../src/wasm2c_rt_mem.c -I../build/_deps/rlbox-src/code/include -I../include -I../build/_deps/mod_wasm2c-src/wasm2c libwebpdecoder.wasm.c
	ar r libwebpdecoder.a libwebpdecoder.wasm.o wasm2c_rt_mem.o wasm2c_rt_minwasi.o wasm-rt-impl.o

sharpyuv: libsharpyuv.wasm
	../build/_deps/mod_wasm2c-src/bin/wasm2c libsharpyuv.wasm -o libsharpyuv.wasm.c
	gcc -c ../build/_deps/mod_wasm2c-src/wasm2c/wasm-rt-impl.c ../src/wasm2c_rt_minwasi.c ../src/wasm2c_rt_mem.c -I../build/_deps/rlbox-src/code/include -I../include -I../build/_deps/mod_wasm2c-src/wasm2c libsharpyuv.wasm.c
	ar r libsharpyuv.a libsharpyuv.wasm.o wasm2c_rt_mem.o wasm2c_rt_minwasi.o wasm-rt-impl.o

clean:
	rm -f *.c *.h *.a *.o
