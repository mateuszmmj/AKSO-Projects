CC = gcc
CFLAGS = -Wall -Wextra -Wpedantic -std=gnu23 -fPIC -O2
LDFLAGS = -shared

TARGET = librstack.so
OBJS = rstack.o

.PHONY: all clean

all: $(TARGET)

$(TARGET): $(OBJS)
	$(CC) $(LDFLAGS) -o $@ $^

rstack.o: rstack.c rstack.h
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS) $(TARGET)
