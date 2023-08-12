CC=g++
CFLAGS= -Wall -Werror -g
LDLIBS=-lm 
OUTPUT=hello
SOURCE=main.cpp hello_world.cpp 

all:codeanalysis hello

codeanalysis: $(SOURCE)
	cppcheck --error-exitcode=1 $^
$(OUTPUT):hello_world.o main.o
	$(CC) $(CFLAGS) $^ $(LDLIBS) -o $(OUTPUT)
hello_world.o : hello_world.cpp
	$(CC)  $(CFLAGS) -c $^ $(LDLIBS) -o $@
main.o : main.cpp
	$(CC) $(CFLAGS) -c $^  $(LDLIBS) -o $@

clean:
	rm *.o $(OUTPUT)
