CC=gcc
CFLAGS=-c -Isrc -Isrc/editline -Isrc/MiniScript
LIBS=-lstdc++ -lm

miniscript: cfiles cppfiles
	g++ -o miniscript *.o

.PHONY: clean

cfiles: src/editline/*.h src/editline/*.c
	gcc -c -std=c99 src/editline/complete.c src/editline/editline.c src/editline/sysunix.c $(LIBS)

cppfiles: src/*.h src/*.cpp src/MiniScript/*.h src/MiniScript/*.cpp
	g++ -c -std=c++11 src/*.h src/*.cpp src/MiniScript/*.cpp -Isrc/editline $(LIBS)

install:
	chmod ugo+x miniscript
	mv miniscript /usr/local/bin

clean:
	rm -f miniscript /usr/local/bin/miniscript
