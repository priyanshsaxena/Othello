ROOTDIR  = ../../
include $(ROOTDIR)Makefile.inc

#CC		 = g++ -rdynamic
#DEBUG    = -O0 -g #-O2 # Uncomment for debug options -O0 -ggdb -pg
#CFLAGS	 = $(DEBUG) -Wall -I$(ROOTDIR)include/ -fPIC
#CXXFLAGS = $(CFLAGS)
#LDFLAGS	 = -g

BOT	= group1
OUT = group1.so

OBJS = $(BOT).o

all: $(OUT)

$(OUT): $(BOT).o $(ROOTDIR)lib/libOthello.so
	$(CC) $(LDFLAGS) -shared $^ -o $@

${OBJS}: %.o : %.cpp 
	$(CC) $(CFLAGS) -c $^ -o $@

.PHONY: clean submission

submission: clean
	zip group1.zip *

clean:
	rm -rf $(OUT)
	rm -rf *.o
