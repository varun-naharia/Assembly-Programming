1. Wirte assembly code in a .asm file
2. Complie and make .o file with following command
	nasm -f macho64 -o hello.o hello.asm
   a. Here -f is used to select output file format.
   b. macho64 is the file format for MacOs 64 bit.
   c. -o hello.h is used to specify output file.
   d. hello.asm is the source file.	
3. Link output file with following command.
	ld -lSystem -e _main -o hello hello.o
   a. Here -lSystem flag is used to fix warning ld: dynamic main executables must link with libSystem.dylib for architecture x86_64 
   b. Here -e _main Specifies the entry point of a main executable.  By default the entry name is "start" which is found in crt1.o which contains the glue code need
                 to set up and call main(). It is the starting point of program that you used in your source code, If you used something else please change it.
   c. -o hello specifies the output and hello.o is the object file genrated in previous step.
4. Run the program with following code.
	./hello 

