all: header library binary

header: mathmini.h

library: static dynamic

static: libmathmini.a

libmathmini.a: mathmini.c
	gcc -c -o mathmini.o mathmini.c
	ar -rcs libmathmini.a mathmini.o

dynamic: libmathmini.dylib libmathmini.so

libmathmini.dylib: mathmini.c
ifeq ($(shell uname -s),Darwin)
	gcc -dynamiclib -o libmathmini.dylib mathmini.c
endif

libmathmini.so: mathmini.c
ifeq ($(shell uname -s),Linux)
	gcc -c -fPIC -o mathmini.o mathmini.c
	gcc -shared -o libmathmini.so mathmini.o
endif

binary: main.c library
	gcc -o mathmini main.c -L. -lmathmini

clean:
	rm -rf mathmini *.o *.a *.dylib *.so
