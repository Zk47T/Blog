# Compiler and flags
CC = gcc
CFLAGS = -Iinclude

# Directories
SRC_DIR = source
INCLUDE_DIR = include
OBJ_DIR = obj
BIN_DIR = bin

# Source files and object files
SRCS = ${wildcard ${SRC_DIR}/*.c}
OBJS = $(SRCS:$(SRC_DIR)/%.c=$(OBJ_DIR)/%.o)

# Output executable
TARGET = main

# Rule to build all
all: $(BIN_DIR)/$(TARGET)

# Link object files to create executable
$(BIN_DIR)/$(TARGET): $(OBJS) | $(BIN_DIR)
	$(CC) $(OBJS) -o $(BIN_DIR)/$(TARGET)

# Compile source files to object files
$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c | $(OBJ_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

# Create obj directory if it doesn't exist
$(OBJ_DIR):
	mkdir -p $(OBJ_DIR)

# Create bin directory if it doesn't exist
$(BIN_DIR):
	mkdir -p $(BIN_DIR)

# Clean up
clean:
	rm -rf $(OBJ_DIR) $(BIN_DIR)

.PHONY: all clean
