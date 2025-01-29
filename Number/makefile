#For this problem, you'll modify the makefile to create a better one.
#
#Add macros for compiler and compiler flags.
#The compiler flags to add are: -c, -Wall, -g, -std=c++11
#Add a macro that defines the object files that should be linked together
#to create the executable.
#Add suffix rule that specifies how to create a .o out of a .C file.
#Modify makefile to use the macros.
#Eliminate unnecessary commands and dependencies. (If the make utility can
#determine a dependence or a command then don't provide it.)
#Use tabs properly or makefile won't work.
#Answer first page of quiz questions using your makefile.
#

CC = g++

#CFLAGS is the compiler flags
CFLAGS = -c -Wall -g -std=c++11

#OBJS is the object files that should be linked together to create the executable
OBJS = makeNumber.o Number.o

#first taret is the final executable
makeNumber: $(OBJS)
	$(CC) $(OBJS) -o makeNumber
	
#rebuild makeNumber.o if makeNumber.C or Number.h changes
makeNumber.o: makeNumber.C Number.h
	$(CC) $(CFLAGS) makeNumber.C

#rebuild Number.p if Number.C or Number.h changes
Number.o: Number.C Number.h
	$(CC) $(CFLAGS) Number.C

# 'make clean' will remove the .o files
clean:
	rm -f *.o









	




