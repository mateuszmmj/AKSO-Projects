NASM = nasm
LD = ld
NASMFLAGS = -f elf64 -w+all -w+error -w-unknown-warning -w-reloc-rel
LDFLAGS = -pie -I /lib64/ld-linux-x86-64.so.2 --fatal-warnings

TARGET = discrete_fractal
OBJ = $(TARGET).o
SRC = $(TARGET).asm

.PHONY: all clean

all: $(TARGET)

$(TARGET): $(OBJ)
	$(LD) $(LDFLAGS) -o $@ $<

$(OBJ): $(SRC)
	$(NASM) $(NASMFLAGS) -o $@ $<

clean:
	rm -f $(OBJ) $(TARGET)
