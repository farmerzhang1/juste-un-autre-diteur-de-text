GCC	= g++
NANAPATH = ~/.local/nana#[The folder of Nana C++ Library]
BIN	= test2#[The bin file what you want to create.]
SOURCES = test2.cpp#[The source file of your application.]

NANAINC	= $(NANAPATH)/include
NANALIB = $(NANAPATH)/build/bin

INCS	= -I $(NANAINC)
LIBS	= -L $(NANALIB) -lnana -lX11 -lpthread -lrt -lXft -lpng -lfontconfig -lasound -lstdc++fs

LINKOBJ	= $(SOURCES:.cpp=.o)

$(BIN): $(LINKOBJ) $(NANALIB)/libnana.a
	$(GCC) $(LINKOBJ) $(INCS) $(LIBS) -o $(BIN) -std=c++11

.cpp.o:
	$(GCC) -g -c $< -o $@ -std=c++0x $(INCS)

$(NANALIB):
	make -f $(NANAPATH)/build/makefile/makefile

clean:
	rm -f $(LINKOBJ)
