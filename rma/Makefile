BIN=./bin/
OBJ=./obj/

# C compiler
CC=mpicc

# MPI
# if required, add paths to mpi.h and any other necessary headers (e.g., UCX)
CFLAGS=
# if required, add paths to ompi libraries and any other necessary libraries
LDFLAGS=

.PHONY: clean

all: test_datatype0.x test_datatype1.x

%.x: %.o
	mkdir -p ${BIN}
	$(CC) -o ${BIN}$@ -L${OBJ} $(LDFLAGS) $(addprefix ${OBJ}, $^) 

%.o: %.c
	mkdir -p ${OBJ}
	$(CC) -c $< -o ${OBJ}$@ $(CFLAGS)

clean:
	rm -f *.o
	rm -f *.x
	rm -f ${OBJ}*.o
	rm -f ${BIN}*.x
	rm -r obj
	rm -r bin
