#cc -std=gnu99 -Wall -Wno-unused-function -Wno-unused-parameter -O2 -DSPF_MAIN -DSPF_DEBUG -DSPF_CACHE=1 -fPIC -c cache.c  dns.c  mem.c  spf.c  zone.c

SHELL = /bin/sh
CC    = cc
FLAGS        = -std=gnu99 
CFLAGS       = -Wall -Wno-unused-function -Wno-unused-parameter 
FLAGS_OPT   = -O2 -DSPF_MAIN -DSPF_CACHE=1 -DSPF_DEBUG -fPIC

FLAGS_LIB    = -std=gnu99 -shared -Wl,-soname

LN = ln -s 

TARGET  = libdns.so
SOURCES = cache.c  dns.c  mem.c  spf.c  zone.c
HEADERS = $(SOURCES:.c=.h)
OBJECTS = $(SOURCES:.c=.o)


all: $(TARGET)

$(TARGET): $(OBJECTS)
	$(CC) $(FLAGS_LIB),$(TARGET).1 -o $(TARGET).1.0 $(OBJECTS)
	$(LN) $(TARGET).1.0 $(TARGET).1
	$(LN) $(TARGET).1.0 $(TARGET)
$(OBJECTS):
	$(CC) $(FLAGS) $(CFLAGS) $(FLAGS_OPT) -c $(SOURCES)
clean:
	rm -rf *.o $(TARGET)*
