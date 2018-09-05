Static libary in c with linux

There are 2 seperate files you need to make bill.c and
fred.c the have simple printf statements

We will now compile the the two files, it is a little diffrent 
then gcc compiling since the files have methods not 
a main function so we have to tell the compliler to only
compile half way by:
    $ cc -c bill.c fred.c 

To list the compiled method:
    $ ls *.o
ex..
    bill.o fred.o

after they are compiled lib.h header file with 2 method
calls:
    void bill(char *)
    void fred(int)

then make a main file with:
    bill("hello");//initializing 

then compile with:
    $ cc -c programMain.c
    $ cc -c programMain programMain.o bill.o
    $ ./programMain
        ex..
            bill: passed hello

to make a archive of methods or library of methods do:
    $ ar crv lib.a bill.o fred.o
        ex..
            //shows what methods are in
            //the archive
            a - bill.o 
            a - fred.o

to make a table of contents for the archive and or 
a index for the library(not used in newer systems but 
wont hurt) run:
    $ runlib lib.a

finally to run the whole program with the archived libary
methods run: 
    $ cc -o main programMain.o lib.a
    $ main
        ex..
            bill: you passed hello 


