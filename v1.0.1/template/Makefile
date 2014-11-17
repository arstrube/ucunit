#
# Sample Makefile for uCUnit
#

#----------------------------------------------------
# Toolchain configuration
#----------------------------------------------------
# Compiler
CC:=gcc
CFLAGS:=-g

#Linker
LD:=gcc
LDFLAGS:=-g

# Simulator/Emulator
RUN:=

# Clean up
RM:=$(RUN) rm

# Echo off
SILENT:=@

#----------------------------------------------------
# Files
#----------------------------------------------------
# Name of target file
TARGET:=./Testsuite.exe

# Sourcefiles
SRCS:=           \
./System.c       \
../Testsuite.c   \

# Objectfiles
OBJS:=           \
./System.obj     \
../Testsuite.obj \

#----------------------------------------------------
# Build all
#----------------------------------------------------
all: $(TARGET)

run: $(TARGET)
	$(SILENT)echo 'Running $(TARGET)...'
	$(RUN) $(TARGET)
	
#----------------------------------------------------
# Linker stage
#----------------------------------------------------
$(TARGET):	$(OBJS)
	$(SILENT)echo 'Linking...'
	$(LD) $(LDFLAGS) -o $(notdir $@) $(notdir $(OBJS))

#----------------------------------------------------
# Compiler
#----------------------------------------------------
%.obj: %.c
	$(SILENT)echo 'Compiling...'
	$(CC) $(CFLAGS) -o $(notdir $@) -c $<
	
#----------------------------------------------------
# Clean Project
#----------------------------------------------------
clean:
	$(SILENT)echo 'Running clean...'
	$(RM) $(TARGET)
	$(RM) System.obj
	$(RM) Testsuite.obj
	$(SILENT)echo 'Clean finished.'
	