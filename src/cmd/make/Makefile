# Description file for the Make command
# Makefile 4.5 94/1/3
TOPSRC		= $(shell cd ../../..; pwd)
include $(TOPSRC)/target.mk
#include $(TOPSRC)/cross.mk

CFLAGS		+= -Werror -Wall -I../ar -g
LDFLAGS         += -g

OBJS            = main.o doname.o misc.o files.o dosys.o y.tab.o

all:            xmake

xmake:          ${OBJS}
		${LD} ${LDFLAGS} -o make.elf ${OBJS} ${LIBS}
		${OBJDUMP} -S make.elf > make.dis
		${SIZE} make.elf
		${ELF2AOUT} make.elf $@ && rm make.elf

clean:
		rm -f *.o *.elf xmake *.elf *.dis tags *~ y.tab.c

install:        all
		install xmake $(DESTDIR)/bin/make

y.tab.c:        gram.y
		$(YACC) gram.y
