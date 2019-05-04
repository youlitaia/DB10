CXX = g++

HEADER_DIR = ../include

FPTREE_HEADER_DIR = $(HEADER_DIR)/fptree

CXXFLAGS = -std=c++11

CFLAGS = -fPIC -std=c99 -O3 -msse4.2 -mpclmul -march=native -funroll-loops -Wstrict-overflow -Wstrict-aliasing -Wall -Wextra -pedantic -Wshadow

MAIN = ./bin/main

YCSB = ./bin/ycsb

LYCSB = ./bin/lycsb

BIN = bin

FPTREE = fptree.o

UTILITY = utility.o

PALLOCATOR = pallocator.o

CLHASH = clhash.o

#ALL := $(LYCSB) $(YCSB) $(MAIN) $(FPTREE) $(UTILITY) $(PALLOCATOR) $(CLHASH)

#============================TODO: all below============================
#$(MAIN) :

#$(FPTREE) : 

#$(UTILITY) :

#$(PALLOCATOR) : pallocator.cpp $(HEADER_DIR)/utility/pallocator.h $(HEADER_DIR)/utility/utility.h
#	$(CXX) $(CXXFLAGS) -c pallocator.cpp -I $(HEADER_DIR) -o $@ -lpmem

$(LYCSB) : lycsb.cpp $(BIN)
	$(CXX) $(CXXFLAGS) lycsb.cpp -o $@ -lleveldb -lpthread

#$(YCSB) :

#$(CLHASH) : clhash.c $(HEADER_DIR)/utility/clhash.h
#	$(CC) $(CFLAGS) -c clhash.c -I $(HEADER_DIR) -g -o $@

$(BIN):
	@mkdir -p bin

all : $(ALL)

clean :
	rm -rf *.o ./bin/* ../data/*
	rm -rf bin

cleand : 
	rm -rf ../data/*