app: main.o calc.o
	gcc main.o calc.o -o app
main.o: main.c calc.h
	gcc -c main.c
calc.o: calc.c calc.h
	gcc -c calc.c
clean:
	r, -f *.o app
