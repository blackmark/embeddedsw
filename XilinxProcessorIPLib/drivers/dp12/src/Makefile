COMPILER=
ARCHIVER=
CP=cp
COMPILER_FLAGS=
EXTRA_COMPILER_FLAGS=-Wall -Wextra
LIB=libxil.a

CC_FLAGS = $(COMPILER_FLAGS)
ECC_FLAGS = $(EXTRA_COMPILER_FLAGS)

RELEASEDIR=../../../lib
INCLUDEDIR=../../../include
INCLUDES=-I./. -I${INCLUDEDIR}

OUTS = *.o

LIBSOURCES:=*.c
INCLUDEFILES:=*.h

OBJECTS =	$(addsuffix .o, $(basename $(wildcard *.c)))

libs: banner xdp_libs clean

%.o: %.c
	${COMPILER} $(CC_FLAGS) $(ECC_FLAGS) $(INCLUDES) -o $@ $<

banner:
	echo "Compiling dp"

xdp_libs: ${OBJECTS}
	$(ARCHIVER) -r ${RELEASEDIR}/${LIB} ${OBJECTS}

.PHONY: include
include: xdp_includes

xdp_includes:
	${CP} ${INCLUDEFILES} ${INCLUDEDIR}

clean:
	rm -rf ${OBJECTS}
