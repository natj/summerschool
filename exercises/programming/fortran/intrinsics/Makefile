COMP=cray

ifeq ($(COMP),cray)
CC=cc
FC=ftn 
FCFLAGS=-efmw -hcpu=sandybridge
endif

ifeq ($(COMP),gnu)
CC=gcc
FC=gfortran
FCFLAGS=-Wall
endif

ifeq ($(COMP),intel)
CC=icc
FC=ifort
endif

EXE=intrinsics
OBJ=intrinsics.o


all: $(EXE)

arrays.o: intrinsics.F90

$(EXE): $(OBJ)
	$(FC) $(FCFLAGS) $(OBJ) -o $@ 

%.o: %.F90
	$(FC) $(FCFLAGS) -c $< -o $@

%.o: %.c
	$(CC) $(CCFLAGS) -c $< -o $@

clean:
	-/bin/rm -f $(EXE)  a.out *.o *.mod *.png *~
