#
# make all cui applications by gcc
#
#export CC = clang
export CC = gcc

BINDIR = /usr/local/bin
DIRS   = pos2kml str2str rnx2rtkp convbin rtkrcv

SRC    = ../../../../src

OPTIONS = -DTRACE -DENAGLO -DENAQZS -DENAGAL -DENACMP -DENAIRN -DNFREQ=6 -DNEXOBS=3

export OPTIONS

DEBUG_CFLAGS = -std=c99 -g -O0 -pedantic -Wall -Wno-unused-but-set-variable $(OPTIONS) -I$(SRC)
RELEASE_CFLAGS = -std=c99 -O3 -pedantic -Wall -Wno-unused-but-set-variable $(OPTIONS) -I$(SRC)


# Get number of parallel build jobs

ifneq ($(shell which nproc 2> /dev/null),)
  NJOBS = $(shell nproc)
else
  NJOBS = 1
endif

# Enable parallel make

PMAKE = make -j $(NJOBS)

all:	release

debug:
	@for i in $(DIRS); do $(PMAKE) -C $$i/gcc CFLAGS='$(DEBUG_CFLAGS)'; done

release:
	@for i in $(DIRS); do $(PMAKE) -C $$i/gcc CFLAGS='$(RELEASE_CFLAGS)'; done


install:
	@echo installing...
	@for i in $(DIRS); do cp $$i/gcc/$$i $(BINDIR); done

clean:
	@echo cleaning up...
	@for i in $(DIRS); do $(PMAKE) -C $$i/gcc clean; done