# Makefile for the Linux graphics to console drivers.

CC = gcc
CFLAGS = -c -Wall 
LDFLAGS =

TARGET = fonts.a

SRCDIR = /usr/src/linux/drivers/video/console/
SOURCES := $(wildcard $(SRCDIR)/font_*.c)
#SOURCES += fonts.c

OBJECTS := $(addprefix ,$(notdir $(SOURCES:.c=.o)))

$(TARGET): $(OBJECTS) fonts.o
	ar rvs $(TARGET) $?
	
%.o: $(SRCDIR)/%.c
	gcc $(CC_FLAGS) -c -o $@ $<

fonts.o: fonts.c
	gcc $(CC_FLAGS) -c -o $@ $<

clean:
	-rm -rf $(TARGET) *.o *~
