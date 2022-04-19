tambahkan folder tempat library SFML ke konfigurasi 'includePath' pada VSCode setting untuk 'C/C++ Configuration'
```
${workspaceFolder}/**
/usr/include/SFML
```

compile tiap folder dengan baris perintah :
```console
g++ -c main.cpp -o {nama_program} -lsfml-window -lsfml-graphics -lsfml-system
```

```
g++ {nama_program} -o {nama_program}_app -lsfml-graphics -lsfml-window -lsfml-system
```

pada folder yang berisikan main.cpp buatlah file Makefile yang berisikan baris seperti berikut
```
all: compile link

compile: 
	g++ -c main.cpp -o main.o -lsfml-window -lsfml-graphics -lsfml-system
link:
	g++ main.o -o main_app -lsfml-graphics -lsfml-window -lsfml-system
clean: 
	rm -f main_app main.o
```

sehingga pada folder tersebut dapat dijalankan baris perintah 
```
make
./main_app
make clean
```