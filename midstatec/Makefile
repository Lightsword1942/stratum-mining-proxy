CC = gcc
CFLAGS =  -Wall -march=armv6 -mfloat-abi=hard -mfpu=vfp -funroll-all-loops -O3 -fstrict-aliasing -std=c99 -I/usr/include/python2.7
LDFLAGS = -Wl,-O1 -Wl,--as-needed -lpython2.7

all: test midstate.so

test: midstatemodule.c
	$(CC) $(CFLAGS)  midstatemodule.c -o test $(LDFLAGS)

midstate.so: midstatemodule.c
	$(CC) $(CFLAGS) -fPIC -shared midstatemodule.c -o midstate.so $(LDFLAGS)

.PHONY: clean

clean:
	rm -f midstate.so test
