# Code Debugging Tools (GBD and Valgrind) Assignment
1) Using Valgind identify memleaks in the given program.Explore optional flags in Valgrind.
   commands
   indentify memory leaks
   ```
   valgrind --leak-check=yes ./output
   ```
   ![val 1](https://github.com/Sharath15eUR/0xAQ/assets/88236255/88107b49-84fd-45e7-88d1-23315ede64f9)

   Explore optional flags
   1) --leak-check=full: Shows a detailed breakdown of each individual memory leak, including the source code location where the leak occurred.
   2) --show-leak-kinds=all: Shows all leak classifications (definite, indirect, possible, reachable) in the "full" leak report.
   3) --track-origins=yes: Tracks the origin of uninitialized values, which can be very helpful for pinpointing memory errors. This can slow down Valgrind execution.
   4) --log-file=filename: Redirects Valgrind's output to a specified file instead of the terminal.
   5) --time-stamp= yes: Add time stamp to log messages.
   6) --show-reachable=yes: Reports whether memory leaks are reachable. 
   ```
   valgrind --leak-check=yes --show-reachable=yes --show-leak-kinds=all --track-origins=yes --time-stamp=yes --log-file=valgrind_log.txt ./output
   ```

2) With the same program, using GDB, set breakpoints, run the program, list the code, run from one breakpoint to another, print the value of variables while execution, check assemble code, disable breakpoints, check registers info, explore optional flags.
set breakpoints
```
break <line no>
break <method name>
```
![gdb 1](https://github.com/Sharath15eUR/0xAQ/assets/88236255/acfab059-7812-4973-871d-7c76005c0e5e)
run the program
```
run
```
run one breakpoint to another 
```
continue
```
print the value of variables while execution
```
print <var name>
```
![gdb 4](https://github.com/Sharath15eUR/0xAQ/assets/88236255/ebfa86ca-255a-4b68-893e-d59a3270e628)
check assemble code
```
disassemable
```
![gdb 5](https://github.com/Sharath15eUR/0xAQ/assets/88236255/a86be25a-2cae-456c-b162-add0833534c4)

disable breakpoints, 
```
disable <break point no>
```
check registers info
```
info register
```
![gdb 6](https://github.com/Sharath15eUR/0xAQ/assets/88236255/55126820-cd66-432a-95f7-01e02bdc1ea8)



