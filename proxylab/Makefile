CC=gcc -m32
CFLAGS=-O2 -Wall
LIBS=-lpthread

FILES = Makefile csapp.h csapp.c echoclient.c echoservert.c echo.c proxy.c echoauto.c

PROGS = echoclient echoserver proxy echoauto

all: $(PROGS)

echoclient: echoclient.c csapp.o csapp.h
	$(CC) $(CFLAGS) -o echoclient echoclient.c csapp.o $(LIBS)

echoserver: echoservert.c csapp.o csapp.h echo.o echo.h
	$(CC) $(CFLAGS) -o echoserver echoservert.c csapp.o echo.o $(LIBS)

proxy: proxy.c csapp.o csapp.h
	$(CC) $(CFLAGS) -o proxy proxy.c csapp.o $(LIBS)

echoauto: echoauto.c csapp.o csapp.h
	$(CC) $(CFLAGS) -o echoauto echoauto.c csapp.o $(LIBS)

only: proxy.c csapp.o csapp.h
	$(CC) $(CFLAGS) -o proxy proxy.c csapp.o $(LIBS)

open1: 
	./echoserver 12345 &

open2:
	./proxy 4321 &

open3:
	./echoclient localhost 4321

csapp.o: csapp.c csapp.h
	$(CC) $(CFLAGS) -c csapp.c

echo.o: echo.c csapp.h
	$(CC) $(CFLAGS) -c echo.c

clean:
	rm -f *.o *~ *.exe *.tar
	rm -f $(PROGS)
