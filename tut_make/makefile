IDIR =../include #Include directory
CC=gcc           #compiler to be used
CFLAGS=-I$(IDIR) #CFLAGS is equivalent to expression in RHS (-I) searches for the header file and writing $(IDIR) searches for the file in the entire include directory

ODIR=obj         # object directory
LDIR =../lib     # library directory

LIBS=-lm         # include math library (will be used for compilation)

_DEPS = hellomake1.h                       # include the dependencies here : header files 
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))    # 

_OBJ = hellomake.o hellofunc.o             # object files (obtained after compiling c files)
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))      # object directory


$(ODIR)/%.o: %.c $(DEPS)                   # these 2 lines say that recompile the object file (left of :) if the dependencies (RHS of :) are changed 
	$(CC) -c -o $@ $< $(CFLAGS)            # gcc -c -o ($@=left of ':' which are the object files names and $< == '.c' and recompile) IN other words .. if header files are changed, remove .o from object files and replace them by .c and recompile

output: $(OBJ)                             # if RHS is changed the output will be executed (NOTE: 'output' can be replaced by any word... just that in the line below it will be used to store compiled output
	gcc -o $@ $^ $(CFLAGS) $(LIBS)         # here the actual compilation occurs

.PHONY: clean                              # won't affect any file named clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~ # make clean will execute this 
