RANLIB	= ranlib
CC	= emcc

CFLAGS=-DPOSIX_MISTAKE

SRCS=	regcomp.c regerror.c regexec.c regfree.c
OBJS=	regcomp.o regerror.o regexec.o regfree.o

all:	libregex.a

libregex.a:	$(OBJS)
	ar ruv libregex.a $(OBJS)
	$(RANLIB) libregex.a

engine.o: engine.c
regcomp.o: regcomp.c utils.h regex2.h cclass.h cname.h
regerror.o: regerror.c utils.h
regexec.o: regexec.c utils.h regex2.h engine.c
regfree.o: regfree.c utils.h regex2.h

clean:
	rm -f *.[ao]

