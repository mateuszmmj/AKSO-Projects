NASM = nasm
NASMFLAGS = -f elf64 -w+all -w+error

TARGET = arithmetic_sequence.o
SRC = arithmetic_sequence.asm

.PHONY: all clean

all: $(TARGET)

$(TARGET): $(SRC)
	$(NASM) $(NASMFLAGS) -o $@ $<

clean:
	rm -f $(TARGET)
