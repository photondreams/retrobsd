TOPSRC		= $(shell cd ../../..; pwd)
include $(TOPSRC)/target.mk

OBJS            = setbrk.o blok.o stak.o cmd.o fault.o main.o word.o \
                  string.o name.o args.o xec.o service.o error.o io.o \
                  print.o macro.o expand.o ctype.o msg.o test.o defs.o \
                  echo.o hash.o hashserv.o pwd.o func.o

all:		sh

sh:		${OBJS}
		${LD} ${LDFLAGS} -o sh.elf ${OBJS} ${LIBS}
		${OBJDUMP} -S sh.elf > sh.dis
		${SIZE} sh.elf
		${ELF2AOUT} sh.elf $@ && rm sh.elf

install:	all
		install sh $(DESTDIR)/bin/

clean:
		rm -f sh *.o *~ *.elf *.dis

args.o: args.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
blok.o: blok.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
cmd.o: cmd.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h sym.h
ctype.o: ctype.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
defs.o: defs.c mode.h name.h
echo.o: echo.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
error.o: error.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
expand.o: expand.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
fault.o: fault.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
func.o: func.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
hash.o: hash.c hash.h defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
hashserv.o: hashserv.c hash.h defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
io.o: io.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h dup.h
macro.o: macro.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h sym.h
main.o: main.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h sym.h timeout.h dup.h
msg.o: msg.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h sym.h
name.o: name.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
print.o: print.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
profile.o: profile.c
pwd.o: pwd.c mac.h defs.h mode.h name.h stak.h brkincr.h ctype.h
service.o: service.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
setbrk.o: setbrk.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
stak.o: stak.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
string.o: string.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
test.o: test.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h
word.o: word.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h sym.h
xec.o: xec.c defs.h mac.h mode.h name.h stak.h brkincr.h ctype.h sym.h hash.h
