# Project name
TARGET = prog21

# Directories
SRC_DIR = src
INC_DIR = include
BUILD_DIR = build

# Source files
SRCS = $(SRC_DIR)/addvec.c $(SRC_DIR)/multvec.c $(SRC_DIR)/main2.c

# Object files
OBJS = $(BUILD_DIR)/addvec.o $(BUILD_DIR)/multvec.o $(BUILD_DIR)/main2.o

# Shared library file
SHARED_LIB = $(BUILD_DIR)/libvector.so

# Compiler and flags
CC = gcc
CFLAGS = -Wall -I$(INC_DIR) -fPIC
LDFLAGS = -shared

# Build target executable
all: $(TARGET)

# Compile main program and link with shared library
$(TARGET): $(BUILD_DIR)/main2.o $(SHARED_LIB)
	$(CC) $(CFLAGS) -o $(TARGET) $(BUILD_DIR)/main2.o -L$(BUILD_DIR) -lvector

# Build shared library
$(SHARED_LIB): $(BUILD_DIR)/addvec.o $(BUILD_DIR)/multvec.o
	$(CC) $(LDFLAGS) -o $(SHARED_LIB) $(BUILD_DIR)/addvec.o $(BUILD_DIR)/multvec.o

# Compile object files for library with -fPIC
$(BUILD_DIR)/addvec.o: $(SRC_DIR)/addvec.c | $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $(SRC_DIR)/addvec.c -o $(BUILD_DIR)/addvec.o

$(BUILD_DIR)/multvec.o: $(SRC_DIR)/multvec.c | $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $(SRC_DIR)/multvec.c -o $(BUILD_DIR)/multvec.o

# Compile main2.o
$(BUILD_DIR)/main2.o: $(SRC_DIR)/main2.c | $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $(SRC_DIR)/main2.c -o $(BUILD_DIR)/main2.o

# Create build directory if it doesn't exist
$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

# Clean up build files
clean:
	rm -rf $(BUILD_DIR) $(TARGET)
