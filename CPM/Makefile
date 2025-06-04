CCPP = g++

SSE_FLAG = -march=native -DWITH_SSE

# Agregamos -Iinclude para que encuentre los headers
CFLAGS = -w -O3 $(SSE_FLAG) -Iinclude

LDFLAGS = $(shell pkg-config --cflags --libs opencv4)

SOURCES_CPP := $(shell find . -name '*.cpp')
OBJ := $(SOURCES_CPP:%.cpp=%.o)
HEADERS := $(shell find . -name '*.h')

all: CPM

.cpp.o: %.cpp %.h
	$(CCPP) -c -o $@ $(CFLAGS) $<

CPM: $(HEADERS) $(OBJ)
	$(CCPP) -o $@ $(OBJ) $(LDFLAGS)

clean:
	rm -f $(OBJ) CPM
