#Create a makefile that will compile the .C files in the source
#directory and create a sortProg executable.
#Add macros for the compiler and the compiler flags.
#The compiler flags to add are: -c, -Wall, -g, -std=c++11, -I ../include
#Add a macro that defines the object files to be linked together
#to create the executable.
#Don't use PATH or the name of any the Linux environment variables
#as a macro name.  (You'll regret it if you do.)
#Add suffix rule that specifies how to create a .o out of a .C file.
#You'll need a target for the executable (sortProg), each .o, install, and clean.
#The very first target in the makefile should be for the executable,
#sortProg.
#Create a bin directory that is at the same level as the source and include directories.
#The install command should create the executable and move it to the ../bin directory.
#The clean command should delete the .o files.
#Do not add unnecessary commands and dependences.
#Answer the questions in the third part of quiz.

CC = g++
# relative path to the include directory
INC = ../include

CFLAGS = -c -Wall -g -std=c++11 -I $(INC)

# object files we want to build and link
OBJS  = sortProg.o Sort.o List.o MergeSort.o QuickSort.o BubbleSort.o

# first target is the final executable
sortProg: $(OBJS)
	$(CC) $(OBJS) -o sortProg

# Compile the driver file (sortProg.C), which includes multiple headers
sortProg.o: sortProg.C $(INC)/Sort.h $(INC)/List.h \
                     $(INC)/MergeSort.h $(INC)/QuickSort.h $(INC)/BubbleSort.h
	$(CC) $(CFLAGS) sortProg.C -o sortProg.o

# Compile each .C file; list their local header dependencies
Sort.o: Sort.C $(INC)/Sort.h
	$(CC) $(CFLAGS) Sort.C -o Sort.o

List.o: List.C $(INC)/List.h
	$(CC) $(CFLAGS) List.C -o List.o

MergeSort.o: MergeSort.C $(INC)/MergeSort.h
	$(CC) $(CFLAGS) MergeSort.C -o MergeSort.o

QuickSort.o: QuickSort.C $(INC)/QuickSort.h
	$(CC) $(CFLAGS) QuickSort.C -o QuickSort.o

BubbleSort.o: BubbleSort.C $(INC)/BubbleSort.h
	$(CC) $(CFLAGS) BubbleSort.C -o BubbleSort.o

# Install target: create ../bin if needed and move the executable there
install:
	mkdir -p ../bin
	mv sortProg ../bin

# Clean target: remove object files and the executable
clean:
	rm -f *.o sortProg
