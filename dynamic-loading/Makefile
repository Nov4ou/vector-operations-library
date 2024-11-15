# Project name
TARGET = prog2r

# Source files and output files
SRCS = addvec.c multvec.c
OBJS = addvec.o multvec.o
SHARED_LIB = libvector.so

# Compiler and flags
CC = gcc
CFLAGS = -Wall -fPIC
LDFLAGS = -shared

# Default target
all: $(SHARED_LIB) $(TARGET)

# Build the shared library libvector.so
$(SHARED_LIB): $(OBJS)
	$(CC) $(LDFLAGS) -o $(SHARED_LIB) $(OBJS)

# Compile object files
%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

# Compile the dynamic loading program
$(TARGET): dll.c
	$(CC) -rdynamic -o $(TARGET) dll.c -ldl

# Clean up generated files
clean:
	rm -f $(TARGET) $(SHARED_LIB) $(OBJS)
