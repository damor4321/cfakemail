SHELL		= /bin/sh
MAKE		= make
DIR_LIBDNS	= $(CURDIR)/../lib/libdns
TARGET_LIBDNS	= libmdns.so
DIR_LIBMILTER	= $(CURDIR)/../lib/libmilter
DIR_INCLUDE	= $(CURDIR)/../include
FLAGS_LIB	=

CC		= cc
FLAGS		= -std=gnu99 -D_REENTRANT
CFLAGS		= -Wall
FLAGS_LIB	= -ldns -lmilter -lpthread
TARGET 		= cfakemail

PREFIX =	/MTA/appn
BINDIR = 	$(PREFIX)/bin
CP		= cp -p

RM	= rm

all: $(TARGET)

$(TARGET): $(TARGET_LIBDNS)
	$(CC) $(FLAGS) $(CFLAGS) -L$(DIR_LIBMILTER) -L$(DIR_LIBDNS) -I$(DIR_INCLUDE) $(TARGET).c $(FLAGS_LIB) -o $(TARGET) 

$(TARGET_LIBDNS):
	$(MAKE) -C $(DIR_LIBDNS)

clean:
	$(RM) $(TARGET)
	$(MAKE) -C $(DIR_LIBDNS) clean

install:
	$(CP) $(TARGET) $(BINDIR)
	
