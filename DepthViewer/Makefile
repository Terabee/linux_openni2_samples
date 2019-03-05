PWD = $(shell pwd)
SRC = ./DepthViewer.cpp
CPPFLAGS = -I../../Include -std=c++11
LDFLAGS = -L$(PWD) -Wl,-rpath ./ -lOpenNI2

# OpenCV
CPPFLAGS += -I/usr/local/include
LDFLAGS += -L/usr/local/lib -lopencv_core -lopencv_highgui -lopencv_imgproc

LOCAL_TARGET = Bin/DepthViewer

all: $(LOCAL_TARGET)

$(LOCAL_TARGET): $(SRC)
	$(CXX) $(SRC) $(CPPFLAGS) $(LDFLAGS) -o $@

clean:
	rm -rf $(LOCAL_TARGET)
