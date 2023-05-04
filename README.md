Download Link: https://assignmentchef.com/product/solved-csci3240-computer-operating-systems-project-5
<br>
Write a program that forks one process. Have the new process execve the program named /usr/bin/bc. Use dup2 and pipes to establish a way for the original process to pass stdin to bc, and to capture its stdout.

It would be a good idea to do alarm(60) in both processes again.

The original process should read lines of input from a file named as the  first command-line arg. Subsequent command-line args should be handed to bc as if they were entered on its command-line; there will be no more than 3.

Each line should be handed to the bc process on its stdin via a pipe, the line input printed, and output (if any) printed like this:

in: line_of_input_from_filebc: output_printed_by_bc # this may be 0 or several linesblank_line

Note that bc will not always print something, e.g. it will not reply to:

a = 0

The select system call can be useful to determine if data is availableon a descriptor. Do not pause more than 1 second for data here.

I will run tests by typing commands like this:

./p5 infilename1./p5 infilename2 -l # the -l will be passed as arg to bc

TURNIN info:You should submit a tar file of a directory which contains all of the required files

(makefile, C source files, header files, etc).Sample tar command to create a tar file from a dir named p5dir:tar cvf p5.tar ./p5dir ## do *NOT* use full pathname of the dirAfter un-tarring your project, I will cd to the dir containingit and type:rm -rf p5rm -f *.omake