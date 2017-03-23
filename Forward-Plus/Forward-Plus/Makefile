OUTPUT   = fwp
SOURCES  = source/main.cpp source/shader.cpp source/camera.cpp source/model.cpp source/mesh.cpp
CXXFLAGS = -std=c++11
LDFLAGS  = -lglfw -lGLEW -lGL -lIL -lassimp
OBJECTS  = $(SOURCES:.cpp=.o)

%.o: %.cpp
	$(CXX) -c $(CXXFLAGS) $< -o $@

all: $(OBJECTS)
	$(CXX) $(OBJECTS) -o $(OUTPUT) -Wl,--whole-archive $(LDFLAGS) -Wl,--no-whole-archive -rdynamic

clean:
	rm -f $(OUTPUT) $(OBJECTS)

.PHONY: clean all
.NOTPARALLEL: clean
