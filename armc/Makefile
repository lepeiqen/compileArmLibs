######################################
#
##
######################################

#target you can change test to what you want
TARGET  := main

#compile and lib parameter
CC      := ~/opt/FriendlyARM/toolschain/4.5.1/bin/arm-none-linux-gnueabi-gcc
LIBS    :=
LDFLAGS := -L. -lcal -ldl
DEFINES :=
INCLUDE := -I.
CFLAGS  := -g -Wall -O3 $(DEFINES) $(INCLUDE)
CXXFLAGS:= $(CFLAGS) -DHAVE_CONFIG_H

#i think you should do anything here

#source file : find all .c/cpp files and subst them to .o files
SOURCE  := $(wildcard *.c) $(wildcard *.cpp)
OBJS    := $(patsubst %.c,%.o,$(patsubst %.cpp,%.o,$(SOURCE)))

.PHONY : everything objs clean veryclean rebuild

everything : $(TARGET)

all : $(TARGET)

objs : $(OBJS)

rebuild: veryclean everything

clean :
	rm -fr *.o $(TARGET)

veryclean : clean
	rm -fr $(TARGET)

$(TARGET) : $(OBJS)
	$(CC) $(CXXFLAGS) -o $@ $(OBJS) $(LDFLAGS) $(LIBS)
