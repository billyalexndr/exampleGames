all: compile link

compile: 
	g++ -c main.cpp -o main.o -lsfml-window -lsfml-graphics -lsfml-system
link:
	g++ main.o -o main_app -lsfml-graphics -lsfml-window -lsfml-system
clean: 
	rm -f main_app main.o
