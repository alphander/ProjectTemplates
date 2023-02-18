# [Settings]
SRC:=src
LIB:=lib
INCLUDE:=include
OBJ:=obj

CC:=clang
RM:=del
OUT:=a.exe

INCLUDES:=-I./$(INCLUDE) -I./$(SRC)
LIBS:=-L./$(LIB)

DEFINES:=

LDFLAGS:=

CFLAGS_ND:=-Wall -O2 -std=c17 -DNDEBUG
CFLAGS_D:=-Wall -g -O0 -std=c17 -DDEBUG

# [Debug and Release rules]

.PHONY: debug release clean build all

all: debug

release: CFLAGS=$(CFLAGS_ND)
release: build

debug: CFLAGS=$(CFLAGS_D)
debug: build

build: $(OUT)

# [Compile C program]

ASSEMBLE=$(CC) $^ -o $@ $(CFLAGS) $(LIBS) $(LDFLAGS)
COMPILE=$(CC) -c $< -o $@ $(CFLAGS) $(INCLUDES) $(DEFINES)

$(OUT):\
	$(OBJ)/main.o
	$(ASSEMBLE)

$(OBJ)/main.o:\
	$(SRC)/main.c
	$(COMPILE)

# [Clean C program]

clean:
	$(RM) $(OUT)
	$(RM) /q $(OBJ)