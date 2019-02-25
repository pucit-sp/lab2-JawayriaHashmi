
filename=         task4
all:result.out
P1=prog1.o
P2=prog2.o
P3=prog3.o
result.out : $(P1) $(P2) $(P3) ./Prog4/prog4.o driver.o
	gcc  driver.o $(P1) $(P2) $(P3) ./Prog4/prog4.o -o myapp
$(P1): prog1.c
	gcc -c prog1.c 
$(P2): prog2.c
	gcc -c prog2.c 
$(P3): prog3.c
	gcc -c prog3.c
include:
	./Prog4/makefile
driver.o: driver.c header.h
	gcc -c -I.  driver.c 
clean:
	rm -f *.o
install: ./${task4}/makefile
	@cp myapp /usr/bin
	@chmod a+x /usr/bin/result.out
	@chmod og-w /usr/bin/result.out
	@echo "result.out successfully installed in /usr/bin"
uninstall:
	@rm -f /usr/bin/myapp
	@echo "result.out successfully un-installed from /usr/bin"

